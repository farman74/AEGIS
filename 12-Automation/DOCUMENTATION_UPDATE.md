# Automatisation — Mise à jour Documentation

## Objectif

Décrire le processus standardisé pour mettre à jour la documentation AEGIS.

## Quand utiliser

À chaque fois que du code est modifié ou qu'une décision est prise.

## Prérequis

- Avoir identifié les documents impactés

## Déclencheur

Code modifié ou décision prise.

## Étapes

1. Identifier les documents impactés
2. Vérifier la cohérence avec `nouvellesnormes.pdf` et `README.md`
3. Mettre à jour les documents concernés
4. Vérifier tous les liens internes
5. Vérifier que toutes les références pointent vers des fichiers existants
6. Vérifier qu'aucune référence à d'anciennes technologies ne subsiste
7. Valider la checklist `09-Checklists/Documentation.md`
8. Inclure la mise à jour dans la même PR que le code
9. Mettre à jour `02-Brain/`

## Résultat

Documentation synchronisée avec le code, cohérente et sans référence cassée.

## Mise à jour Brain

- Enregistrer les modifications majeures de documentation.

## Références

- `09-Checklists/Documentation.md`
- `10-Templates/Documentation.md`
