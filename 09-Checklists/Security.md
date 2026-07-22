# Checklist — Security

## Objectif

Vérifier qu'un livrable respecte les standards de sécurité AEGIS avant validation.

## Quand utiliser

Avant toute Pull Request touchant à l'authentification, aux permissions, aux données sensibles ou aux API.

## Prérequis

- Avoir lu `05-Engineering/Security/RULES.md`

## Procédure

- [ ] L'authentification passe par Supabase Auth uniquement
- [ ] Les politiques RLS sont actives sur toutes les tables sensibles
- [ ] Aucune clé secrète n'est exposée côté client
- [ ] Les variables d'environnement sont utilisées pour les secrets
- [ ] Les permissions sont vérifiées côté serveur
- [ ] Les accès sont tracés dans le journal d'audit
- [ ] Les données des candidats sont anonymisées là où nécessaire
- [ ] Les injections SQL sont impossibles (paramètres liés)
- [ ] Les uploads sont validés (type, taille, contenu)
- [ ] Les actions critiques sont journalisées

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `05-Engineering/Security/RULES.md`
- `04-Agents/Security/CHECKLIST.md`
