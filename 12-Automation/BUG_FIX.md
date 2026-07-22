# Automatisation — Correction de Bug

## Objectif

Décrire le processus standardisé pour corriger un bug dans ExamOS.

## Quand utiliser

À chaque fois qu'un bug est identifié et doit être corrigé.

## Prérequis

- Issue créée avec `10-Templates/Issue.md`
- Bug reproduit et documenté

## Déclencheur

Bug confirmé et assigné.

## Étapes

1. Reproduire le bug
2. Identifier la cause racine
3. Consulter les règles techniques concernées dans `05-Engineering/`
4. Identifier l'impact sur les autres modules
5. Corriger le bug
6. Écrire un test de non-régression
7. Valider la checklist concernée dans `09-Checklists/`
8. Mettre à jour la documentation si nécessaire
9. Ouvrir une Pull Request (`10-Templates/PR.md`)
10. Passer par `03-Orchestration/REVIEW_PIPELINE.md`
11. Mettre à jour `02-Brain/`

## Résultat

Bug corrigé, test de non-régression ajouté, documentation mise à jour.

## Mise à jour Brain

- Enregistrer la cause racine
- Enregistrer la solution appliquée
- Mettre à jour l'état du projet

## Références

- `10-Templates/Issue.md`
- `09-Checklists/Testing.md`
