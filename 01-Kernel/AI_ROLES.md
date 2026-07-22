# AI ROLES

Version : 1.0
Status : Active

---

## Objectif

Définir les rôles et responsabilités de chaque agent IA dans ExamOS.

## Quand utiliser

Quand un agent doit identifier son rôle ou déléguer une tâche.

## Prérequis

- `01-Kernel/AI_SYSTEM.md` lu.

## Procédure

### Rôles définis

| Rôle | Responsabilité | Dossier de référence |
|---|---|---|
| Orchestrateur | Analyse, routage, planification | `03-Orchestration/` |
| Architecte | Décisions d'architecture | `04-Agents/Architecture/` |
| Backend | API, logique serveur (Supabase) | `04-Agents/Backend/` |
| Database | Schémas Supabase, migrations | `04-Agents/Database/` |
| Frontend | UI, composants | `04-Agents/Frontend/` |
| OCR | Numérisation copies | `04-Agents/OCR/` |
| IA | Modèles, prompts, correction | `04-Agents/AI/` |
| Sécurité | Auth, RBAC, audit | `04-Agents/Security/` |
| Testing | Tests, qualité | `04-Agents/Testing/` |
| Documentation | Docs, Brain | `04-Agents/Documentation/` |
| Review | Revue, validation | `04-Agents/Review/` |

### Règle de délégation

Un agent ne peut travailler que dans son domaine.
Si une tâche dépasse son domaine, il la délègue via `03-Orchestration/AGENT_ROUTER.md`.

## Validation

- [ ] Le rôle actuel est identifié
- [ ] Les limites du rôle sont connues

## Références

- `03-Orchestration/AGENT_ROUTER.md`
- `04-Agents/`
