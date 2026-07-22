# Checklist — Frontend

## Objectif

Vérifier qu'un livrable frontend respecte les standards AEGIS avant validation.

## Quand utiliser

Avant de soumettre une Pull Request contenant du code frontend (composants, pages, hooks).

## Prérequis

- Avoir lu `05-Engineering/Frontend/RULES.md`

## Procédure

- [ ] Les composants sont atomiques et réutilisables
- [ ] Aucune logique métier dans les composants UI
- [ ] La gestion des états est propre
- [ ] Les erreurs sont affichées à l'utilisateur
- [ ] Les formulaires sont validés côté client
- [ ] L'accessibilité de base est respectée
- [ ] Les appels API passent par les services dédiés
- [ ] La connexion à Supabase passe par le client officiel
- [ ] Aucune clé API exposée côté client
- [ ] Les tests sont écrits
- [ ] La documentation des composants est mise à jour
- [ ] Aucun `console.log` laissé en production

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `05-Engineering/Frontend/RULES.md`
- `09-Checklists/Testing.md`
