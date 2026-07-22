# Database Best Practices

## Objectif

Fournir les meilleures pratiques pour toute interaction avec la base de données Supabase d'ExamOS. Ce document est le complément positif de `RULES.md` (ce qui est obligatoire) et de `ANTI_PATTERNS.md` (ce qui est interdit).

## Quand utiliser

Avant de concevoir un schéma, écrire une migration, créer une policy ou optimiser une requête Supabase.

## Prérequis

- `05-Engineering/Database/RULES.md` lu
- `05-Engineering/Database/ANTI_PATTERNS.md` lu
- `02-Brain/ADR/ADR-001-supabase.md` lu

---

## Principes fondamentaux

1. **Supabase-first** : Toute décision database part de Supabase. Aucune autre technologie n'est envisagée.
2. **Sécurité par défaut** : RLS activé dès la création de chaque table. Pas de table non protégée.
3. **Données jamais perdues** : Soft delete systématique. Toute donnée est récupérable.
4. **Traçabilité totale** : Toute action importante crée un enregistrement dans `audit_logs`.
5. **IA-first** : Les schémas sont conçus pour être lisibles et exploitables par des agents IA.

---

## Architecture Database AEGIS

ExamOS utilise Supabase comme couche database unique. Les composants utilisés :

| Composant | Rôle |
|---|---|
| Supabase Database | Données métier relationnelles |
| Supabase Auth | Authentification + gestion des rôles |
| Supabase Storage | Copies scannées, PDF, images |
| Supabase Realtime | Notifications temps réel, suivi correction |
| Supabase Edge Functions | Logique serverless légère |

**Architecture multi-tenant** : chaque table métier possède un `organization_id`. Cela garantit l'isolation totale des données entre organisations (ministères, écoles, universités).

---

## Supabase Guidelines

### Utilisation du client Supabase

- Utiliser le client officiel Supabase (`@supabase/supabase-js`) côté frontend.
- Pour les opérations sensibles (logique métier critique, batch), préférer les **Edge Functions** Supabase.
- Ne jamais exposer la `service_role` key côté client. Utiliser uniquement la clé `anon` avec RLS.

### Supabase Auth

- Utiliser exclusivement Supabase Auth pour l'authentification.
- Les rôles utilisateur (`CORRECTOR`, `ADMIN`, etc.) sont stockés dans la table `profiles` liée à `auth.users`.
- Accéder à `auth.uid()` dans les policies RLS pour identifier l'utilisateur courant.

### Supabase Storage

- Stocker les fichiers volumineux (copies PDF, images scannées) dans Supabase Storage.
- Stocker uniquement l'URL publique ou le chemin dans la table `copies`.
- Organiser le stockage : `/{organization_id}/{year}/{exam_id}/{copy_id}.pdf`.

### Supabase Realtime

- Activer Realtime uniquement sur les tables nécessitant des mises à jour en direct (`corrections`, `ai_jobs`).
- Filtrer les abonnements Realtime par `organization_id` pour éviter les fuites inter-organisations.

---

## Database Design

### Nommage

- Tables : `snake_case` au pluriel (`exam_sessions`, `ai_corrections`)
- Colonnes : `snake_case` (`created_at`, `organization_id`, `deleted_at`)
- Index : `idx_{table}_{colonne}` (`idx_candidates_exam_id`)
- Fonctions : `snake_case` descriptif (`get_active_exams_by_org`)

### Colonnes obligatoires sur chaque table

```sql
id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
organization_id UUID NOT NULL REFERENCES organizations(id),
created_at TIMESTAMPTZ DEFAULT NOW(),
updated_at TIMESTAMPTZ DEFAULT NOW(),
deleted_at TIMESTAMPTZ
```

### Relations

- Toujours définir les clés étrangères explicitement.
- Préférer `ON DELETE RESTRICT` pour les données critiques (examens, copies).
- Utiliser `ON DELETE CASCADE` uniquement pour des données de détail sans valeur légale autonome.

### Types de données recommandés

| Donnée | Type recommandé |
|---|---|
| Identifiant | `UUID` |
| Timestamp | `TIMESTAMPTZ` |
| Montant / score | `NUMERIC(5,2)` |
| Données JSON variables | `JSONB` |
| Statut / enum | `TEXT` + contrainte `CHECK` |
| Texte long (OCR) | `TEXT` |

---

## Schema Management

### Migrations

- Chaque modification de schéma fait l'objet d'une migration nommée avec timestamp : `2026_07_22_create_copies_table.sql`.
- Toute migration possède un fichier `up` et un fichier `down` (rollback).
- Les migrations sont vérifiées en environnement de développement avant d'être appliquées en production.
- Ne jamais modifier manuellement le schéma en production via le dashboard Supabase sans migration correspondante.

### Versioning

- Les barèmes (`rubrics`) et les prompts IA sont versionnés (`version INTEGER`).
- Les données sensibles modifiées (scores, validations) enregistrent l'ancien et le nouveau état dans `audit_logs`.

### Environnements

| Environnement | Usage |
|---|---|
| `development` | Développement local, tests de migrations |
| `staging` | Validation avant production |
| `production` | Données réelles, accès restreint |

- Ne jamais tester une migration directement en production.
- Les seeds de données de test n'ont aucun accès à la base production.

---

## Security Rules

### Row Level Security (RLS)

- **RLS activé sur toutes les tables** contenant des données métier ou personnelles.
- Aucune table ne reste ouverte sans policy explicite.
- Par défaut : accès refusé. Les policies accordent les droits de façon granulaire.

### Policies Supabase — Modèles recommandés

**Policy lecture — utilisateur de la même organisation :**
```sql
CREATE POLICY "select_own_org"
ON copies FOR SELECT
USING (organization_id = get_user_organization_id());
```

**Policy écriture — rôle spécifique :**
```sql
CREATE POLICY "corrector_can_update_score"
ON human_reviews FOR UPDATE
USING (reviewer_id = auth.uid());
```

**Policy insertion — authentifié uniquement :**
```sql
CREATE POLICY "authenticated_insert"
ON exam_sessions FOR INSERT
WITH CHECK (auth.role() = 'authenticated');
```

### Séparation des rôles

- `anon` : Lecture des données publiques uniquement (résultats publiés).
- `authenticated` : Accès selon le rôle métier défini dans `profiles`.
- `service_role` : Réservé aux Edge Functions et aux opérations d'administration.

---

## Performance

### Indexation

- Créer des index sur toutes les colonnes utilisées en filtre fréquent : `organization_id`, `exam_id`, `status`, `candidate_id`.
- Utiliser des index partiels pour les données actives : `WHERE deleted_at IS NULL`.
- Surveiller les index inutilisés via les vues de statistiques Supabase.

### Requêtes

- Toujours filtrer par `organization_id` en premier pour profiter du multi-tenant.
- Utiliser `select()` avec projection explicite des colonnes (éviter `SELECT *`).
- Paginer les résultats avec `.range(from, to)` pour les listes longues.
- Préférer les vues matérialisées pour les statistiques lourdes calculées fréquemment.

### Optimisation JSONB

- Indexer les champs JSONB fréquemment filtrés : `CREATE INDEX idx_ai_criteria ON ai_corrections USING GIN (analysis)`.
- Ne pas stocker en JSONB ce qui peut être normalisé en colonnes relationnelles.

---

## Scalability

- **Partitionnement** : Pour les grandes tables (`copies`, `audit_logs`), partitionner par année (`copies_2026`, `copies_2027`).
- **Archivage** : Les données de plus de N années sont déplacées vers des tables d'archive (`archived_copies`).
- **Connection pooling** : Utiliser le connection pooler Supabase (PgBouncer) pour les environnements à fort trafic.
- **Lecture/écriture** : Séparer les requêtes analytiques lourdes sur un replica en lecture si disponible.

---

## Backup and Recovery

- Supabase fournit des sauvegardes automatiques quotidiennes (point-in-time recovery sur les plans Pro+).
- Configurer des exports manuels hebdomadaires pour les données critiques (résultats, copies validées).
- Tester la procédure de restauration en environnement de staging au moins une fois par trimestre.
- Ne jamais supprimer physiquement (`TRUNCATE`, `DROP TABLE`) sans avoir vérifié la sauvegarde récente.
- **RPO cible** : 5 minutes. **RTO cible** : 1 heure.

---

## AI Development Rules

Règles spécifiques pour les agents IA qui génèrent ou modifient du code database :

1. **Lire RULES.md et ANTI_PATTERNS.md avant toute action** sur le schéma.
2. **Ne jamais générer de migration sans rollback** correspondant.
3. **Toujours inclure `organization_id`** dans les tables métier créées.
4. **Toujours activer RLS** sur les tables créées et définir au moins une policy.
5. **Ne jamais utiliser d'entiers comme PK** ; utiliser `UUID DEFAULT gen_random_uuid()`.
6. **Ne jamais recommander PostgreSQL local, Prisma, Firebase ou MongoDB.**
7. **Valider le schéma généré** contre la checklist ci-dessous avant de soumettre.
8. **Documenter chaque table créée** : objectif, colonnes principales, policies RLS associées.

---

## Validation Checklist

- [ ] Supabase est l'unique base de données
- [ ] UUID utilisé comme clé primaire sur toutes les tables
- [ ] `organization_id` présent sur toutes les tables métier
- [ ] `created_at`, `updated_at`, `deleted_at` présents
- [ ] RLS activé sur toutes les tables sensibles
- [ ] Policies RLS définies et testées
- [ ] Migrations réversibles (up + down)
- [ ] Index créés sur les colonnes filtrées fréquemment
- [ ] Fichiers stockés dans Supabase Storage (pas en base)
- [ ] Aucun entier utilisé comme ID
- [ ] Soft delete utilisé (pas de DELETE physique)
- [ ] Données sensibles tracées dans `audit_logs`
- [ ] Environnements development / staging / production séparés

---

## References

- `05-Engineering/Database/RULES.md`
- `05-Engineering/Database/ANTI_PATTERNS.md`
- `05-Engineering/Database/TESTING.md`
- `02-Brain/ADR/ADR-001-supabase.md`
- `04-Agents/Database/CHECKLIST.md`
- `06-Playbooks/Database/`
