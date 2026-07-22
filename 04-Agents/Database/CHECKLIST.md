# Checklist Agent Database (Supabase)

Avant de valider un schéma ou une migration :

- [ ] Supabase est la seule base de données utilisée
- [ ] Intégrité référentielle respectée
- [ ] Migrations réversibles (rollback possible)
- [ ] UUID utilisés pour les IDs
- [ ] Soft delete implémenté (deleted_at)
- [ ] Audit logs configurés
- [ ] Index documentés
- [ ] Row Level Security (RLS) activé
- [ ] Aucune référence à PostgreSQL local, SQLite, Firebase, MongoDB
- [ ] Schéma documenté dans Brain
