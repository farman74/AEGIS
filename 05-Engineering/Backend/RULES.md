# Règles Backend

## Objectif

Règles techniques obligatoires pour tout développement Backend dans ExamOS.

## Quand utiliser

Avant et pendant tout développement Backend.

## Procédure

### Règles fondamentales

1. Le Backend utilise exclusivement le **client Supabase officiel** pour accéder aux données.
2. Aucune connexion directe à PostgreSQL n'est autorisée (pas de pg, pg-promise, Knex, Sequelize).
3. L'authentification utilise **Supabase Auth** exclusivement.
4. Les fichiers sont stockés via **Supabase Storage** exclusivement.
5. La logique métier complexe peut utiliser des **Supabase Edge Functions**.
6. Chaque API est versée et documentée.
7. Chaque erreur est gérée et loggée.
8. Aucun secret en dur dans le code (utiliser les variables d'environnement Supabase).

### Règles de structure

- Un module = une responsabilité
- Les APIs respectent le template `10-Templates/API.md`
- Pas de logique métier dans les contrôleurs

## Validation

- [ ] Client Supabase officiel utilisé
- [ ] Supabase Auth utilisé
- [ ] Aucun secret en dur
- [ ] Erreurs gérées

## Références

- `05-Engineering/Database/RULES.md`
- `05-Engineering/API/RULES.md`
