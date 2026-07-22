# Checklist — Backend

## Objectif

Vérifier qu'un livrable backend respecte les standards AEGIS avant validation.

## Quand utiliser

Avant de soumettre une Pull Request contenant du code backend (API, services, logique métier).

## Prérequis

- Avoir lu `05-Engineering/Backend/RULES.md`
- Avoir lu `05-Engineering/API/RULES.md`

## Procédure

- [ ] Respect de l'architecture définie
- [ ] Toutes les erreurs sont gérées explicitement
- [ ] Les logs sont en place
- [ ] La validation des entrées est effectuée
- [ ] Les tests unitaires sont écrits
- [ ] Les tests d'intégration sont écrits
- [ ] La documentation est mise à jour
- [ ] Aucune logique métier dans les controllers
- [ ] Aucune duplication de code
- [ ] Les permissions sont vérifiées
- [ ] La connexion à la base de données passe par Supabase uniquement
- [ ] Aucune référence à PostgreSQL local, SQLite, Firebase, MongoDB ou Prisma
- [ ] Les API Resources sont utilisées (pas de retour de modèles bruts)
- [ ] Aucun TODO oublié

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `05-Engineering/Backend/RULES.md`
- `05-Engineering/API/RULES.md`
- `09-Checklists/Testing.md`
