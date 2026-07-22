# 01-Kernel

## Objectif

Contient les protocoles que toute IA doit suivre pour interagir avec le projet ExamOS.
Ce dossier est le "système d'exploitation" du comportement IA.

## Structure

```
01-Kernel/
├── README.md
├── AI_SYSTEM.md
├── AI_ROLES.md
├── MEMORY_PROTOCOL.md
├── CONTEXT_PROTOCOL.md
├── TASK_PROTOCOL.md
├── REVIEW_PROTOCOL.md
├── DECISION_PROTOCOL.md
├── COMMUNICATION_PROTOCOL.md
└── QUALITY_GATES.md
```

## Comment utiliser

Lire dans l'ordre :
1. `AI_SYSTEM.md` — comprendre le système global
2. `AI_ROLES.md` — identifier son rôle
3. `CONTEXT_PROTOCOL.md` — charger le contexte
4. `TASK_PROTOCOL.md` — exécuter la tâche

## Liens avec les autres dossiers

- Dépend de `00-Core/` pour les valeurs et principes.
- Alimente `02-Brain/` avec les décisions.
- Orchestre `03-Orchestration/` via les protocoles.
