# Anti-Patterns Database — À éviter absolument

## Objectif

Lister les erreurs à ne jamais commettre dans la base de données ExamOS.

## Quand utiliser

Pendant la revue d'un schéma ou d'une migration.

## Procédure

### Anti-Patterns interdits

**AP-001 — Utiliser une base de données autre que Supabase**
- Interdit : PostgreSQL local, SQLite, Firebase, MongoDB, Prisma ORM seul
- Correct : Supabase (PostgreSQL managé)

**AP-002 — Stocker des fichiers binaires dans la base**
- Interdit : Stocker des PDF ou images directement dans PostgreSQL
- Correct : Utiliser Supabase Storage + stocker l'URL dans la table

**AP-003 — Supprimer physiquement des données**
- Interdit : `DELETE FROM copies WHERE id = ?`
- Correct : `UPDATE copies SET deleted_at = NOW() WHERE id = ?`

**AP-004 — Utiliser des integers comme IDs**
- Interdit : `id INTEGER AUTO_INCREMENT`
- Correct : `id UUID DEFAULT gen_random_uuid()`

**AP-005 — Désactiver RLS**
- Interdit : Tables avec données sensibles sans RLS
- Correct : RLS activé + policies définies

**AP-006 — Migrations irréversibles**
- Interdit : Migration sans rollback possible
- Correct : Toujours prévoir la migration inverse

## Validation

- [ ] Aucun de ces anti-patterns n'est présent

## Références

- `05-Engineering/Database/RULES.md`
