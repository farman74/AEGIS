# Checklist — Documentation

## Objectif

Vérifier qu'un document AEGIS est complet, cohérent et conforme aux nouvelles normes avant validation.

## Quand utiliser

Avant de soumettre ou mettre à jour tout document du dépôt AEGIS.

## Prérequis

- Avoir lu `00-Core/QUALITY_STANDARD.md`

## Procédure

- [ ] Le document suit la structure standard (`# Objectif` / `# Quand utiliser` / `# Prérequis` / `# Procédure` / `# Validation` / `# Références`)
- [ ] Le titre est explicite et conforme aux conventions de nommage
- [ ] Aucune référence à une ancienne architecture
- [ ] Aucune référence à PostgreSQL local, SQLite, Firebase, MongoDB ou Prisma
- [ ] Tous les liens internes pointent vers des fichiers existants
- [ ] Tous les chemins mentionnés correspondent à des fichiers réels
- [ ] Aucun doublon avec un autre document existant
- [ ] Le document est prévu par `nouvellesnormes.pdf` ou `README.md`
- [ ] Le document est mis à jour dans la même PR que le code associé

## Validation

Tous les points doivent être cochés avant de considérer le document comme terminé.

## Références

- `00-Core/QUALITY_STANDARD.md`
- `10-Templates/Documentation.md`
