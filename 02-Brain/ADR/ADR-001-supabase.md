# ADR-001 — Adoption de Supabase comme base de données

**Date** : 2026-07-22
**Statut** : Accepté
**Décideur** : AI CTO

---

## Contexte

ExamOS a besoin d'une solution de persistance capable de gérer :
- Authentification multi-rôles
- Stockage de fichiers (copies scannées, PDF)
- Notifications temps réel
- Logs d'audit
- Accès multi-tenant

## Décision

**ExamOS utilise exclusivement Supabase.**

Components Supabase utilisés :
- **Supabase Database** (PostgreSQL managé) — toutes les données métier
- **Supabase Auth** — authentification, RBAC
- **Supabase Storage** — copies scannées, PDF, images
- **Supabase Realtime** — notifications, suivi en temps réel
- **Supabase Edge Functions** — logique serverless légère

## Raisons

1. PostgreSQL managé — pas de maintenance infrastructure
2. Auth intégré avec RBAC natif
3. Storage intégré pour les fichiers volumineux
4. Realtime natif pour le suivi des corrections
5. Écosystème cohérent et réduit la complexité

## Alternatives rejetées

| Alternative | Raison du rejet |
|---|---|
| PostgreSQL local | Infrastructure à gérer, pas de Auth/Storage intégré |
| SQLite | Non scalable pour une plateforme nationale |
| Firebase | Pas relationnel, modèle de données inadapté |
| MongoDB | Non relationnel, contraintes d'intégrité absentes |
| Prisma seul | ORM uniquement, pas une base de données |

## Conséquences

- Tous les schémas sont créés dans Supabase Dashboard ou via migrations SQL Supabase.
- Toute référence à une autre base dans la documentation doit être supprimée.
- Les agents Database utilisent les outils Supabase (CLI, client JS/Python).

## Références

- `01-Kernel/DECISION_PROTOCOL.md`
- `05-Engineering/Database/RULES.md`
