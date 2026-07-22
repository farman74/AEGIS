# EXECUTION PIPELINE

Version : 1.0
Status : Active

---

## Objectif

Décrire exactement le cycle d'exécution d'une tâche.

## Quand utiliser

Pour chaque tâche, après le routage et la planification.

## Procédure

### Cycle obligatoire

```
1. ANALYSE
   Lire la tâche + charger le contexte (CONTEXT_MANAGER)
   ↓
2. PLANIFICATION
   Décomposer si nécessaire (TASK_PLANNER)
   ↓
3. EXÉCUTION
   Suivre le Playbook correspondant (06-Playbooks)
   Appliquer les règles (05-Engineering)
   Utiliser les patterns (08-Patterns)
   Consulter les DecisionTrees (07-DecisionTrees)
   ↓
4. AUTO-VÉRIFICATION
   Valider la checklist du domaine (09-Checklists)
   ↓
5. REVIEW
   Appliquer REVIEW_PIPELINE
   ↓
6. DOCUMENTATION
   Mettre à jour les docs avec les templates (10-Templates)
   ↓
7. BRAIN UPDATE
   Mettre à jour 02-Brain (STATE + DECISIONS)
```

L'ordre ne change jamais.

## Validation

- [ ] Les 7 étapes ont été suivies dans l'ordre
- [ ] Aucune étape n'a été sautée

## Références

- `01-Kernel/TASK_PROTOCOL.md`
- `06-Playbooks/`
- `02-Brain/`
