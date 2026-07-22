# Automatisation — Revue de Code

## Objectif

Décrire le processus standardisé pour effectuer une revue de code dans ExamOS.

## Quand utiliser

À chaque fois qu'une Pull Request est soumise.

## Prérequis

- Pull Request ouverte avec `10-Templates/PR.md`

## Déclencheur

Pull Request ouverte.

## Étapes

1. Lire la description de la PR
2. Vérifier que le Feature Contract est respecté
3. Consulter `03-Orchestration/REVIEW_PIPELINE.md`
4. Vérifier les checklists concernées dans `09-Checklists/`
5. Analyser le code : architecture, sécurité, performance, lisibilité
6. Vérifier que Supabase est utilisé exclusivement pour la base de données
7. Vérifier les tests
8. Vérifier la documentation
9. Approuver ou demander des modifications
10. Mettre à jour `02-Brain/` si une décision architecturale a été prise

## Résultat

PR approuvée ou retours précis fournis.

## Mise à jour Brain

- Enregistrer les décisions architecturales prises pendant la revue.

## Références

- `03-Orchestration/REVIEW_PIPELINE.md`
- `09-Checklists/Review.md`
