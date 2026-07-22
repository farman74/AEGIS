# CONTEXT PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir quels documents lire, dans quel ordre, pour charger le contexte complet avant une tâche.

## Quand utiliser

Obligatoirement au début de chaque session ou avant de démarrer une tâche importante.

## Procédure

### Ordre de lecture obligatoire

```
1. README.md                           ← Vue globale
2. 00-Core/PROJECT_CONSTITUTION.md     ← La loi
3. 00-Core/ENGINEERING_PRINCIPLES.md   ← Les règles
4. 00-Core/AI_MANIFESTO.md             ← Le comportement
5. 02-Brain/STATE.md                   ← État actuel
6. 02-Brain/DECISIONS.md               ← Décisions prises
7. 03-Orchestration/AGENT_ROUTER.md    ← Routage
8. [Document spécifique à la tâche]   ← Contexte local
```

### Documents par domaine

| Domaine | Documents à lire |
|---|---|
| Backend | `05-Engineering/Backend/RULES.md` + Playbook correspondant |
| Database | `05-Engineering/Database/RULES.md` + schémas Supabase dans Brain |
| Frontend | `05-Engineering/Frontend/RULES.md` + Playbook |
| IA | `05-Engineering/AI/RULES.md` + `04-Agents/AI/` |
| Sécurité | `05-Engineering/Security/RULES.md` |

## Validation

- [ ] README.md lu
- [ ] 00-Core complet lu
- [ ] 02-Brain consulté
- [ ] Document spécifique chargé

## Références

- `01-Kernel/MEMORY_PROTOCOL.md`
- `02-Brain/`
