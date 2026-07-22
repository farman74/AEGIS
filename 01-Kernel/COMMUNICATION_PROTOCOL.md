# COMMUNICATION PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir comment un agent IA communique avec l'humain et avec les autres agents.

## Quand utiliser

Dès qu'un agent doit communiquer un résultat, un blocage ou une décision.

## Procédure

### Communication avec l'humain

**Structure standard d'un message IA :**
```
[CONTEXTE] : Ce que l'IA a compris
[ACTION] : Ce que l'IA a fait
[RÉSULTAT] : Ce qui a été produit
[VALIDATION] : Ce que l'humain doit valider
[BLOCAGE] : Ce qui bloque (si applicable)
```

### Communication entre agents

- Passer par `03-Orchestration/AGENT_ROUTER.md`
- Utiliser les contrats définis dans `10-Templates/`
- Ne jamais communiquer directement sans passer par l'Orchestrateur

### Règles de ton

- Précis et factuel
- Sans suppositions non documentées
- Toujours indiquer la source de l'information (quel document AEGIS)

## Validation

- [ ] Le message respecte la structure standard
- [ ] Les sources sont citées

## Références

- `03-Orchestration/AGENT_ROUTER.md`
