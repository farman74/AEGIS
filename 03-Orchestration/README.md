# 03-Orchestration

## Objectif

Faire en sorte que toutes les demandes passent par un pipeline unique.
Aucune tâche n'est exécutée directement par un agent sans passer par ce pipeline.

## Structure

```
03-Orchestration/
├── README.md
├── AGENT_ROUTER.md
├── TASK_PLANNER.md
├── EXECUTION_PIPELINE.md
├── CONTEXT_MANAGER.md
└── REVIEW_PIPELINE.md
```

## Comment utiliser

1. Toute demande entre par `AGENT_ROUTER.md`.
2. Si la demande est complexe, utiliser `TASK_PLANNER.md`.
3. Exécuter selon `EXECUTION_PIPELINE.md`.
4. Gérer le contexte avec `CONTEXT_MANAGER.md`.
5. Valider avec `REVIEW_PIPELINE.md`.

## Liens avec les autres dossiers

- Reçoit les demandes de l'utilisateur.
- Délègue aux agents de `04-Agents/`.
- S'appuie sur les règles de `05-Engineering/`.
- Met à jour `02-Brain/` après exécution.
