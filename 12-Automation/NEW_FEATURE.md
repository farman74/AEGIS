# Automatisation — Nouvelle Fonctionnalité

## Objectif

Décrire le processus standardisé pour créer une nouvelle fonctionnalité dans ExamOS.

## Quand utiliser

À chaque fois qu'une nouvelle fonctionnalité doit être développée.

## Prérequis

- Feature Contract validé (`10-Templates/Feature.md`)
- Issue créée (`10-Templates/Issue.md`)

## Déclencheur

Feature Contract approuvé par l'humain.

## Étapes

1. Lire le Feature Contract complet
2. Consulter `03-Orchestration/AGENT_ROUTER.md` pour identifier les agents concernés
3. Consulter `03-Orchestration/TASK_PLANNER.md` pour décomposer la tâche
4. Lire les Playbooks correspondants dans `06-Playbooks/`
5. Lire les règles techniques dans `05-Engineering/`
6. Développer Backend
7. Développer Frontend
8. Écrire les tests
9. Valider les checklists concernées dans `09-Checklists/`
10. Mettre à jour la documentation
11. Ouvrir une Pull Request (`10-Templates/PR.md`)
12. Passer par `03-Orchestration/REVIEW_PIPELINE.md`
13. Mettre à jour `02-Brain/`

## Résultat

Fonctionnalité livrée, testée, documentée et archivée dans le Brain.

## Mise à jour Brain

- Enregistrer la décision dans `02-Brain/`
- Mettre à jour l'état d'avancement du projet

## Références

- `03-Orchestration/TASK_PLANNER.md`
- `10-Templates/Feature.md`
- `09-Checklists/Review.md`
