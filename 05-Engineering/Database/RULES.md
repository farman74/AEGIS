# Règles Database — Supabase

## Objectif

Règles techniques obligatoires pour toute interaction avec la base de données Supabase d'ExamOS.

## Quand utiliser

Avant et pendant tout travail sur les tables, les migrations ou les requêtes Supabase.

## Prérequis

- `02-Brain/ADR/ADR-001-supabase.md` lu
- Accès Supabase projet ExamOS

## Procédure

### Règles de base

1. **Supabase uniquement** : Aucune autre base (PostgreSQL local, SQLite, Firebase, MongoDB) n'est autorisée.
2. **UUID** : Toutes les tables utilisent des UUID comme clé primaire.
3. **Soft Delete** : Toute suppression utilise `deleted_at TIMESTAMPTZ` au lieu d'une suppression physique.
4. **Timestamps** : Toute table possède `created_at` et `updated_at`.
5. **RLS activé** : Row Level Security activé sur toutes les tables contenant des données sensibles.
6. **Migrations réversibles** : Tout changement de schéma a un rollback possible.
7. **organization_id** : Toute table métier possède un `organization_id` (architecture multi-tenant).

### Règles de nommage

- Tables : `snake_case` au pluriel (ex : `exam_sessions`, `candidates`)
- Colonnes : `snake_case` (ex : `created_at`, `organization_id`)
- Fonctions : `snake_case` descriptif (ex : `get_exam_by_id`)
- Index : `idx_table_colonne` (ex : `idx_candidates_exam_id`)

### Règles de sécurité Supabase

- Auth : Utiliser **Supabase Auth** exclusivement
- Permissions : Définies via **RLS policies** dans Supabase
- Storage : Utiliser **Supabase Storage** pour les fichiers volumineux (copies, PDF)
- Audit : Utiliser les logs Supabase + table `audit_logs` métier

### Composants Supabase autorisés

| Composant | Usage dans ExamOS |
|---|---|
| Supabase Database | Toutes les données métier |
| Supabase Auth | Authentification + RBAC |
| Supabase Storage | Copies scannées, PDF, images |
| Supabase Realtime | Notifications, suivi correction |
| Supabase Edge Functions | Logique serverless légère |

## Validation

- [ ] Supabase est la seule base de données
- [ ] UUID utilisé comme PK
- [ ] RLS activé
- [ ] Soft delete implémenté
- [ ] Migrations réversibles

## Références

- `02-Brain/ADR/ADR-001-supabase.md`
- `04-Agents/Database/CHECKLIST.md`
