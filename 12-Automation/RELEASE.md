# Automatisation — Release

## Objectif

Décrire le processus standardisé pour livrer une version d'ExamOS.

## Quand utiliser

À chaque préparation d'une nouvelle version.

## Prérequis

- Toutes les fonctionnalités prévues sont terminées et validées
- Tous les tests passent

## Déclencheur

Décision de livraison validée par l'humain.

## Étapes

1. Vérifier que tous les Quality Gates sont passés (`00-Core/QUALITY_STANDARD.md`)
2. Valider toutes les checklists dans `09-Checklists/`
3. Vérifier la cohérence complète du dépôt (liens, références, arborescence)
4. Confirmer que Supabase est bien configuré pour l'environnement cible
5. Générer le changelog
6. Taguer la version
7. Déployer
8. Vérifier le bon fonctionnement en production
9. Mettre à jour `02-Brain/` avec l'état post-release

## Résultat

Version livrée, stable et documentée.

## Mise à jour Brain

- Enregistrer la version livrée
- Enregistrer les décisions prises pendant la release
- Mettre à jour l'état d'avancement du projet

## Références

- `00-Core/QUALITY_STANDARD.md`
- `09-Checklists/Review.md`
- `02-Brain/`
