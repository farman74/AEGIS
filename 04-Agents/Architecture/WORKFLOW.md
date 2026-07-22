# Agent Architecture — Workflow

## Objectif

Décrire le processus exact que suit l'Agent Architecture pour traiter une tâche.

## Workflow

```
Réception de la demande
    ↓
Lecture du contexte (00-Core + 01-Kernel + 02-Brain)
    ↓
Analyse de l'impact architectural
    ↓
Consultation de 05-Engineering/Architecture/RULES.md
    ↓
Consultation de 08-Patterns/Architecture/
    ↓
Consultation de 07-DecisionTrees/Architecture/
    ↓
Proposition de solution
    ↓
Rédaction de l'ADR si nécessaire (10-Templates/ADR.md)
    ↓
Validation humaine
    ↓
Mise à jour de 02-Brain/
```

## Règles

- Toute décision architecturale requiert un ADR
- Aucune modification de l'architecture sans validation humaine
- La persistance utilise exclusivement Supabase

## Références

- `03-Orchestration/EXECUTION_PIPELINE.md`
- `05-Engineering/Architecture/RULES.md`
