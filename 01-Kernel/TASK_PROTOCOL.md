# TASK PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir comment un agent IA doit traiter une tâche du début à la fin.

## Quand utiliser

Dès qu'une tâche est assignée à un agent.

## Procédure

### Étapes obligatoires

```
1. ANALYSE
   - Lire la tâche complètement
   - Identifier le domaine (Backend, Frontend, Database…)
   - Charger le contexte (CONTEXT_PROTOCOL.md)
   - Identifier les risques

2. PLANIFICATION
   - Décomposer la tâche si nécessaire (TASK_PLANNER)
   - Identifier les dépendances
   - Vérifier les préconditions

3. EXÉCUTION
   - Suivre le Playbook correspondant dans 06-Playbooks/
   - Respecter les règles de 05-Engineering/
   - Utiliser les Patterns de 08-Patterns/
   - Consulter les DecisionTrees de 07-DecisionTrees/ si nécessaire

4. AUTO-VÉRIFICATION
   - Valider la checklist de 09-Checklists/
   - Vérifier les références et les liens
   - Vérifier la cohérence avec l'architecture

5. REVIEW
   - Appliquer REVIEW_PROTOCOL.md

6. DOCUMENTATION
   - Mettre à jour les documents concernés
   - Utiliser les templates de 10-Templates/

7. BRAIN UPDATE
   - Mettre à jour 02-Brain/STATE.md et DECISIONS.md
```

## Validation

- [ ] Les 7 étapes ont été suivies
- [ ] La checklist du domaine est validée
- [ ] Le Brain est mis à jour

## Références

- `03-Orchestration/EXECUTION_PIPELINE.md`
- `06-Playbooks/`
- `09-Checklists/`
