# AGENT ROUTER

Version : 1.0
Status : Active

---

## Objectif

Déterminer quel agent utiliser, dans quel ordre, et quels agents peuvent travailler en parallèle.

## Quand utiliser

Premier document consulté à chaque nouvelle demande.

## Procédure

### Table de routage

| Type de demande | Agent principal | Agents secondaires |
|---|---|---|
| Nouvelle feature | Architecte | Backend, Database, Frontend, Testing, Documentation |
| Correction d'un bug | Agent du domaine concerné | Review |
| Modification de schéma Supabase | Database | Backend, Testing |
| Nouvelle API | Backend | Database, Testing, Documentation |
| Composant UI | Frontend | Testing |
| Nouveau prompt IA | AI | Testing |
| Amélioration OCR | OCR | AI, Testing |
| Audit sécurité | Sécurité | Review |
| Mise à jour documentation | Documentation | Review |

### Règles de parallélisme

Peuvent travailler en parallèle :
- Backend + Frontend (si les contrats API sont définis)
- Testing + Documentation

Doivent travailler séquentiellement :
- Database → Backend (le schème Supabase avant les APIs)
- Architecture → tout le reste
- Backend → Frontend (API d'abord)

## Validation

- [ ] L'agent principal est identifié
- [ ] Les agents secondaires sont identifiés
- [ ] L'ordre d'exécution est défini

## Références

- `04-Agents/`
- `03-Orchestration/TASK_PLANNER.md`
