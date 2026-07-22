# Agent Backend — Responsabilités

## Objectif

Définir les responsabilités exactes de l'Agent Backend.

## Responsabilités

1. Implémenter les endpoints API d'ExamOS
2. Développer les Services métier
3. Intégrer Supabase (Database, Auth, Storage, Realtime)
4. Écrire les tests unitaires et d'intégration
5. Gérer les jobs asynchrones (corrections longues)
6. Implémenter les notifications
7. S'assurer que toutes les erreurs sont gérées
8. Documenter chaque endpoint (`10-Templates/API.md`)

## Ce que cet agent ne fait PAS

- Ne définit pas l'architecture (rôle de l'Agent Architecture)
- N'utilise pas de base de données autre que Supabase
- Ne code pas le Frontend

## Références

- `05-Engineering/Backend/RULES.md`
- `05-Engineering/API/RULES.md`
