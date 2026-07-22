# 04-Agents

## Objectif

Décrit les spécialistes IA du projet ExamOS. Chaque agent est responsable d'un domaine précis.

## Structure

```
04-Agents/
├── README.md
├── Architecture/
│   ├── README.md
│   ├── MISSION.md
│   ├── RESPONSIBILITIES.md
│   ├── WORKFLOW.md
│   ├── INPUTS.md
│   ├── OUTPUTS.md
│   └── CHECKLIST.md
├── Backend/      (même structure)
├── Database/     (même structure)
├── Frontend/     (même structure)
├── OCR/          (même structure)
├── AI/           (même structure)
├── Security/     (même structure)
├── Testing/      (même structure)
├── Documentation/(même structure)
└── Review/       (même structure)
```

Tous les agents ont exactement la même structure interne.

## Convention de structure d'un agent

Chaque dossier agent contient :

| Fichier | Rôle |
|---|---|
| `README.md` | Vue générale de l'agent |
| `MISSION.md` | Ce que l'agent doit accomplir |
| `RESPONSIBILITIES.md` | Responsabilités précises |
| `WORKFLOW.md` | Étape par étape |
| `INPUTS.md` | Ce que l'agent reçoit |
| `OUTPUTS.md` | Ce que l'agent produit |
| `CHECKLIST.md` | Validation avant livraison |

## Comment utiliser

1. Consulter `03-Orchestration/AGENT_ROUTER.md` pour identifier l'agent à utiliser.
2. Lire `MISSION.md` + `WORKFLOW.md` de l'agent concerné.
3. Exécuter selon le Playbook correspondant dans `06-Playbooks/`.

## Liens avec les autres dossiers

- Reçoit ses tâches de `03-Orchestration/`
- S'appuie sur les règles de `05-Engineering/`
- Suit les Playbooks de `06-Playbooks/`
- Valide avec les Checklists de `09-Checklists/`
