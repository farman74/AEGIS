# Database Testing

## Objectif

Définir les pratiques de test pour la base de données Supabase d'ExamOS. Ce document couvre la validation des schémas, des policies RLS, des migrations, de l'intégrité des données et du code généré par IA.

## Quand utiliser

Avant tout merge touchant le schéma, les policies, les migrations ou les requêtes Supabase.

## Prérequis

- `05-Engineering/Database/RULES.md` lu
- `05-Engineering/Database/BEST_PRACTICES.md` lu
- Environnement de test Supabase (projet dédié ou branch) disponible

---

## Types de tests

| Type | Objectif | Fréquence |
|---|---|---|
| Unit Tests | Tester fonctions et logique isolée | À chaque PR |
| Integration Tests | Tester les interactions entre tables | À chaque PR |
| Security Tests | Valider RLS et policies | À chaque modification de policy |
| Performance Tests | Mesurer les temps de requête | Avant mise en production |
| Migration Tests | Valider up et rollback | À chaque migration |
| Data Validation Tests | Contrôler l'intégrité des données | Continu |

---

## Unit Tests

### Périmètre

Tester les éléments atomiques : fonctions SQL, triggers, contraintes.

### Pratiques

- Tester chaque fonction SQL avec des données d'entrée variées (cas nominal, cas limite, cas d'erreur).
- Vérifier les contraintes `CHECK` : valeurs acceptées et valeurs rejetées.
- Tester les triggers (`updated_at`, soft delete) de façon isolée.
- Utiliser des données de test générées par des factories, jamais des données de production.

### Exemple — Test contrainte UUID

```sql
-- Vérifier que l'UUID est bien généré automatiquement
INSERT INTO exam_sessions (organization_id, name)
VALUES ('org-uuid-test', 'Test Session');

SELECT id FROM exam_sessions WHERE name = 'Test Session';
-- Résultat attendu : UUID non nul, format valide
```

### Exemple — Test soft delete

```sql
-- Vérifier que deleted_at est défini au lieu d'une suppression physique
UPDATE copies SET deleted_at = NOW() WHERE id = 'copy-uuid-test';

SELECT COUNT(*) FROM copies WHERE id = 'copy-uuid-test' AND deleted_at IS NOT NULL;
-- Résultat attendu : 1
```

---

## Integration Tests

### Périmètre

Tester les interactions entre tables, les jointures, les cascades de clés étrangères.

### Pratiques

- Créer un jeu de données cohérent couvrant le workflow complet : organisation → examen → matière → candidat → copie → correction IA → validation humaine.
- Vérifier que la suppression (soft) d'une entité parente ne brise pas les requêtes enfants.
- Tester les requêtes complexes avec filtres `organization_id` + `exam_id` + `status`.
- Valider la pagination (`.range()`) sur les tables à volume important.

### Exemple — Test relation copies → ai_corrections

```sql
-- Vérifier qu'une copie peut toujours être récupérée avec sa correction IA
SELECT c.id, ac.score, ac.confidence
FROM copies c
LEFT JOIN ai_corrections ac ON ac.copy_id = c.id
WHERE c.organization_id = 'org-uuid-test'
  AND c.deleted_at IS NULL
  AND c.status = 'AI_CORRECTED';
-- Résultat attendu : lignes retournées avec scores non nuls
```

---

## Supabase Testing

### Environnement de test

- Utiliser un projet Supabase dédié aux tests (jamais le projet de production).
- Si disponible, utiliser les **Supabase Database Branches** pour isoler les tests par PR.
- Réinitialiser les données de test après chaque suite (`TRUNCATE` + reseed) en environnement de test uniquement.

### Test du client Supabase

- Tester les appels via `@supabase/supabase-js` avec des utilisateurs de test authentifiés.
- Vérifier que les réponses correspondent au schéma attendu (types, colonnes).
- Tester les cas d'erreur Supabase : clé étrangère violée, contrainte violée, timeout.

### Test Supabase Realtime

- Vérifier que les events Realtime sont bien déclenchés lors des INSERT/UPDATE sur les tables configurées.
- Vérifier que le filtre `organization_id` empêche la réception d'events inter-organisations.

---

## Security Testing

### RLS — Row Level Security

Les tests de sécurité sont **obligatoires** avant tout déploiement en production.

**Principe : tester chaque policy avec le rôle ciblé ET avec un rôle non autorisé.**

#### Test accès inter-organisations (isolation multi-tenant)

```sql
-- Utilisateur authentifié avec organization_id = 'org-A'
-- Ne doit PAS voir les données de 'org-B'
SELECT COUNT(*) FROM copies
WHERE organization_id = 'org-B-uuid';
-- Résultat attendu : 0 (RLS bloque l'accès)
```

#### Test policy correcteur

```sql
-- Un correcteur ne doit voir que ses propres corrections
-- Connecté en tant que correcteur-X
SELECT COUNT(*) FROM human_reviews
WHERE reviewer_id != auth.uid();
-- Résultat attendu : 0
```

#### Test accès anonyme

```sql
-- Un utilisateur non authentifié ne doit accéder à aucune donnée sensible
-- (rôle anon)
SELECT COUNT(*) FROM candidates;
-- Résultat attendu : erreur RLS ou 0 selon la policy définie
```

### Checklist sécurité avant déploiement

- [ ] RLS activé sur toutes les tables testées
- [ ] Accès inter-organisations bloqué
- [ ] Utilisateur anonyme ne voit pas les données sensibles
- [ ] Chaque rôle métier n'accède qu'à son périmètre
- [ ] La `service_role` key n'est pas utilisée côté client

---

## Performance Testing

### Objectifs

- Identifier les requêtes lentes avant la mise en production.
- Valider que les index créés sont bien utilisés par le query planner.

### Pratiques

- Utiliser `EXPLAIN ANALYZE` pour vérifier le plan d'exécution des requêtes critiques.
- Tester les requêtes avec un volume représentatif (jeux de données de 10 000+ lignes minimum pour les tables copies et audit_logs).
- Mesurer le temps de réponse des endpoints Supabase avec des outils de load testing (k6, Artillery).

### Seuils recommandés

| Opération | Seuil acceptable |
|---|---|
| Lecture simple (filtre PK) | < 50 ms |
| Liste paginée (100 lignes) | < 200 ms |
| Requête analytique complexe | < 2 000 ms |
| Upload + insertion métadonnées | < 500 ms |

### Exemple — Vérification index

```sql
EXPLAIN ANALYZE
SELECT * FROM copies
WHERE organization_id = 'org-uuid'
  AND exam_id = 'exam-uuid'
  AND deleted_at IS NULL
LIMIT 50;
-- Vérifier que le plan utilise un Index Scan et non un Seq Scan
```

---

## Data Validation

### Intégrité des données

- Vérifier après chaque migration que les contraintes `NOT NULL`, `UNIQUE` et `CHECK` sont respectées.
- Valider que les scores IA (`ai_corrections.score`) restent dans les bornes définies par le barème.
- Contrôler que tout enregistrement de `copies` possède un `candidate_id` valide et un `exam_id` valide.

### Tests de cohérence métier

- Vérifier qu'une copie au statut `VALIDATED` possède bien un enregistrement dans `human_reviews`.
- Vérifier que les résultats publiés (`published_results`) correspondent aux copies validées.
- Contrôler que `audit_logs` contient bien un enregistrement pour chaque modification de score.

### Exemple — Vérification cohérence score/validation

```sql
-- Toute copie VALIDATED doit avoir un human_review
SELECT COUNT(*) FROM copies c
LEFT JOIN human_reviews hr ON hr.copy_id = c.id
WHERE c.status = 'VALIDATED'
  AND hr.id IS NULL
  AND c.deleted_at IS NULL;
-- Résultat attendu : 0
```

---

## AI Generated Code Validation

Les agents IA qui génèrent du code database (migrations, policies, queries) doivent passer les validations suivantes avant tout merge :

### Checklist validation code IA

1. **Conformité RULES.md** : Le code généré ne viole aucune règle (UUID, soft delete, RLS, Supabase uniquement).
2. **Absence d'anti-patterns** : Aucun `DELETE` physique, aucun entier comme PK, aucune technologie interdite.
3. **Rollback présent** : Toute migration générée possède son script de rollback.
4. **RLS défini** : Si une nouvelle table est créée, la policy RLS correspondante est générée et testée.
5. **Tests d'isolation** : Le code IA a été exécuté sur l'environnement de test (jamais directement en production).
6. **Review humaine** : Un développeur humain valide le code généré avant merge.

### Processus de validation IA

```
Code généré par IA
        ↓
Vérification RULES.md + ANTI_PATTERNS.md
        ↓
Exécution sur environnement de test
        ↓
Tests unitaires + sécurité RLS
        ↓
Review humaine
        ↓
Merge autorisé
```

---

## Test Checklist

### Avant chaque PR touchant la database

- [ ] Migrations testées (up) sur environnement de test
- [ ] Rollback testé (down) sur environnement de test
- [ ] RLS policies testées (accès autorisé + accès bloqué)
- [ ] Isolation multi-tenant vérifiée (accès inter-organisations impossible)
- [ ] Contraintes et types de données vérifiés
- [ ] Intégrité référentielle vérifiée
- [ ] Performance des requêtes critiques mesurée
- [ ] Code généré par IA validé par un humain
- [ ] Aucun anti-pattern introduit
- [ ] `audit_logs` alimenté pour les actions sensibles

---

## References

- `05-Engineering/Database/RULES.md`
- `05-Engineering/Database/BEST_PRACTICES.md`
- `05-Engineering/Database/ANTI_PATTERNS.md`
- `02-Brain/ADR/ADR-001-supabase.md`
- `04-Agents/Database/CHECKLIST.md`
- `06-Playbooks/Database/`
