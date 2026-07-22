# DECISION PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir comment prendre et documenter une décision technique.

## Quand utiliser

Chaque fois qu'une décision technique importante est prise.

## Procédure

### Types de décisions

| Type | Traitement |
|---|---|
| Décision architecturale | ADR obligatoire dans `02-Brain/ADR/` |
| Choix technique mineur | Documenté dans `02-Brain/DECISIONS.md` |
| Choix standard | Utiliser `07-DecisionTrees/` |

### Format ADR (Architecture Decision Record)

Utiliser le template `10-Templates/ADR.md`.

Chaque ADR contient :
- Contexte
- Décision prise
- Raisons
- Alternatives considérées
- Conséquences
- Statut (Proposé / Accepté / Rejeté / Remplacé)

### Règle de base de données

La décision Supabase est **définitive et non-revisée**.
Toute autre base de données (PostgreSQL local, SQLite, Firebase, MongoDB, Prisma) est interdite.

## Validation

- [ ] Le type de décision est identifié
- [ ] La décision est documentée dans le bon endroit
- [ ] Le Brain est mis à jour

## Références

- `02-Brain/ADR/`
- `10-Templates/ADR.md`
- `07-DecisionTrees/`
