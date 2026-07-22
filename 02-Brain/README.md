# 02-Brain

## Objectif

Contient la mémoire vivante du projet ExamOS. Ce dossier est mis à jour après chaque session de travail.

C'est la source de vérité sur l'état actuel : décisions prises, progression, problèmes connus, contraintes découvertes.

## Structure

```
02-Brain/
├── README.md
├── STATE.md        ← État actuel du projet
├── DECISIONS.md    ← Toutes les décisions prises
└── ADR/            ← Architecture Decision Records
    └── ADR-001-supabase.md
```

## Comment utiliser

- **Lire** avant chaque session de travail.
- **Écrire** après chaque décision importante.
- **Créer un ADR** après chaque décision architecturale.

## Liens avec les autres dossiers

- Alimenté par tous les agents après chaque tâche.
- Lu par `01-Kernel/CONTEXT_PROTOCOL.md` en début de session.
- Les ADR utilisent le template `10-Templates/ADR.md`.
