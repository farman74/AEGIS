# 09-Checklists

## Objectif

Permettre aux agents IA de vérifier leur travail avant de soumettre un livrable.
Chaque checklist couvre un domaine précis et doit être validée avant toute Pull Request ou livraison.

## Structure

```
09-Checklists/
├── README.md
├── Architecture.md
├── Backend.md
├── Frontend.md
├── Database.md
├── OCR.md
├── Security.md
├── Testing.md
├── Documentation.md
└── Review.md
```

## Comment utiliser

1. Identifier le domaine de la tâche terminée.
2. Ouvrir la checklist correspondante.
3. Valider chaque point.
4. Ne soumettre le livrable que si tous les points sont cochés.

## Liens avec les autres dossiers

- `04-Agents/` : Chaque agent utilise les checklists de son domaine avant de terminer.
- `03-Orchestration/REVIEW_PIPELINE.md` : La revue s'appuie sur ces checklists.
- `10-Templates/` : Les livrables produits doivent passer les checklists correspondantes.
