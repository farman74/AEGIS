# CONTEXT MANAGER

Version : 1.0
Status : Active

---

## Objectif

Définir quels documents lire en fonction de la tâche, et comment mettre à jour le Brain.

## Quand utiliser

Étape 1 du pipeline : avant toute exécution.

## Procédure

### Chargement du contexte

**Contexte minimal (toujours) :**
1. `README.md`
2. `00-Core/PROJECT_CONSTITUTION.md`
3. `02-Brain/STATE.md`
4. `02-Brain/DECISIONS.md`

**Contexte par domaine (selon la tâche) :**

| Domaine | Documents additionnels |
|---|---|
| Backend | `05-Engineering/Backend/RULES.md` |
| Database (Supabase) | `05-Engineering/Database/RULES.md` + `02-Brain/ADR/ADR-001-supabase.md` |
| Frontend | `05-Engineering/Frontend/RULES.md` |
| IA | `04-Agents/AI/MISSION.md` + `05-Engineering/AI/RULES.md` |
| Sécurité | `05-Engineering/Security/RULES.md` |

### Mise à jour du Brain

Après chaque tâche :
1. Documenter la décision dans `02-Brain/DECISIONS.md`
2. Mettre à jour `02-Brain/STATE.md`
3. Créer un ADR si nécessaire

## Validation

- [ ] Contexte minimal chargé
- [ ] Contexte du domaine chargé
- [ ] Brain mis à jour en fin de tâche

## Références

- `01-Kernel/CONTEXT_PROTOCOL.md`
- `01-Kernel/MEMORY_PROTOCOL.md`
- `02-Brain/`
