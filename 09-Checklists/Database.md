# Checklist — Database

## Objectif

Vérifier qu'une modification de base de données respecte les standards AEGIS et la migration Supabase.

## Quand utiliser

Avant toute création ou modification de table, vue, fonction ou politique RLS dans Supabase.

## Prérequis

- Avoir lu `05-Engineering/Database/RULES.md`

## Procédure

- [ ] La migration utilise Supabase exclusivement
- [ ] Aucune référence à PostgreSQL local, SQLite, Firebase, MongoDB ou Prisma
- [ ] L'intégrité référentielle est respectée
- [ ] Les migrations sont réversibles
- [ ] Les index sont documentés et justifiés
- [ ] Les contraintes sont explicites
- [ ] La normalisation est adaptée au besoin
- [ ] Les politiques RLS (Row Level Security) sont définies
- [ ] Les colonnes `created_at` et `updated_at` sont présentes
- [ ] L'auditabilité est assurée
- [ ] Le schéma est documenté

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `05-Engineering/Database/RULES.md`
- `05-Engineering/Database/BEST_PRACTICES.md`
