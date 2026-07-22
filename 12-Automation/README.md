# 12-Automation

## Objectif

Décrire les automatisations internes standardisées du projet ExamOS.
Chaque automatisation réduit le risque d'erreur humaine et alimente systématiquement le Brain.

## Structure

```
12-Automation/
├── README.md
├── NEW_FEATURE.md
├── BUG_FIX.md
├── CODE_REVIEW.md
├── DOCUMENTATION_UPDATE.md
└── RELEASE.md
```

## Comment utiliser

1. Identifier le type d'opération à réaliser.
2. Ouvrir l'automatisation correspondante.
3. Suivre les étapes dans l'ordre exact.
4. Mettre à jour `02-Brain/` à la fin.

## Format standard de chaque automatisation

```
# Déclencheur
# Étapes
# Résultat
# Mise à jour Brain
```

## Liens avec les autres dossiers

- `03-Orchestration/` : L'orchestration déclenche les automatisations.
- `02-Brain/` : Toutes les automatisations mettent à jour le Brain.
- `09-Checklists/` : Chaque automatisation vérifie la checklist avant de terminer.
