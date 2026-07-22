# Checklist — Architecture

## Objectif

Vérifier qu'une décision ou livrable d'architecture respecte les standards AEGIS avant validation.

## Quand utiliser

Avant de soumettre un ADR, une décision de design ou une modification structurelle.

## Prérequis

- Avoir lu `00-Core/ENGINEERING_PRINCIPLES.md`
- Avoir consulté `05-Engineering/Architecture/RULES.md`

## Procédure

- [ ] Le besoin métier est clairement identifié
- [ ] L'architecture respecte les principes AEGIS (modularity, loose coupling, high cohesion)
- [ ] Aucune duplication de responsabilité
- [ ] Les dépendances entre modules sont explicites
- [ ] La décision est documentée dans un ADR (`10-Templates/ADR.md`)
- [ ] Aucune référence à PostgreSQL local, SQLite, Firebase, MongoDB ou Prisma
- [ ] La persistance utilise exclusivement Supabase
- [ ] Les risques sont identifiés
- [ ] L'impact sur les autres modules est évalué

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `00-Core/ENGINEERING_PRINCIPLES.md`
- `05-Engineering/Architecture/RULES.md`
- `10-Templates/ADR.md`
