# MEMORY PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir comment un agent IA mémorise et rappelle le contexte du projet.

## Quand utiliser

Au début et à la fin de chaque session de travail.

## Prérequis

- `01-Kernel/AI_SYSTEM.md` lu.
- Accès à `02-Brain/`.

## Procédure

### Au début d'une session

1. Lire `02-Brain/STATE.md` — état actuel du projet
2. Lire `02-Brain/DECISIONS.md` — décisions prises
3. Lire `02-Brain/ADR/` — Architecture Decision Records
4. Charger le contexte de la tâche concernée

### En fin de session

1. Documenter les décisions prises dans `02-Brain/DECISIONS.md`
2. Mettre à jour `02-Brain/STATE.md`
3. Créer un ADR si une décision architecturale a été prise
4. Mettre à jour le document concerné si nécessaire

### Ce qui doit être mémorisé

- Décisions techniques
- Choix d'architecture
- Problèmes rencontrés et solutions
- État d'avancement des fonctionnalités
- Contraintes découvertes

## Validation

- [ ] Brain lu en début de session
- [ ] Brain mis à jour en fin de session

## Références

- `02-Brain/`
- `10-Templates/ADR.md`
