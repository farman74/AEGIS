# AI MANIFESTO

Version : 1.0
Status : Active
Owner : AI CTO

---

## Objectif

Ce document définit les règles de comportement obligatoires pour tout agent IA travaillant sur ExamOS.

Ce manifeste s'applique à : Cursor, Claude Code, Codex, Copilot, et tout autre agent IA futur.

## Quand utiliser

Ce document doit être lu par toute IA au début de chaque session de travail.

## Prérequis

- `00-Core/PROJECT_CONSTITUTION.md` lu.
- `00-Core/ENGINEERING_PRINCIPLES.md` lu.
- `02-Brain/` consulté pour l'état actuel.

## Procédure

### Règles de comportement

**Avant de travailler :**
1. Lire le contexte complet (AEGIS + 02-Brain)
2. Comprendre le métier ExamOS
3. Identifier les risques de la tâche
4. Vérifier les décisions existantes dans 02-Brain
5. Consulter le Playbook correspondant dans 06-Playbooks

**Pendant le travail :**
6. Respecter strictement les principes d'ingénierie
7. Ne jamais inventer une règle métier
8. Ne jamais modifier l'architecture sans ADR
9. Expliquer chaque choix important
10. Préférer la simplicité à la complexité

**Après le travail :**
11. Mettre à jour la documentation
12. Mettre à jour 02-Brain avec les décisions prises
13. Valider la checklist correspondante dans 09-Checklists

### Interdictions absolues

- Inventer une architecture
- Créer un fichier non prévu par AEGIS
- Ajouter des fonctionnalités non demandées
- Modifier la philosophie du projet
- Ignorer les nouvelles normes
- Utiliser une base de données autre que Supabase
- Faire des suppositions sans les documenter

### En cas de doute

Appliquer uniquement ce qui est écrit dans AEGIS.
Si l'information n'est pas dans AEGIS, demander à l'humain.

## Validation

Une IA qui respecte ce manifeste :
- [ ] A lu tout AEGIS avant de commencer
- [ ] Ne fait aucune supposition non documentée
- [ ] Met à jour le Brain en fin de session
- [ ] Respecte les 20 principes d'ingénierie

## Références

- `00-Core/PROJECT_CONSTITUTION.md`
- `00-Core/ENGINEERING_PRINCIPLES.md`
- `01-Kernel/CONTEXT_PROTOCOL.md`
- `02-Brain/`
