# TASK PLANNER

Version : 1.0
Status : Active

---

## Objectif

Décomposer une grosse demande en sous-tâches assignées aux bons agents.

## Quand utiliser

Quand une demande concerne plusieurs domaines ou plusieurs agents.

## Procédure

### Décomposition standard d'une nouvelle feature

```
Nouvelle feature
    ↓
[Architecte] Définir l'architecture
    ↓
[Database]   Créer/modifier les tables Supabase
    ↓
[Backend]    Créer les API
    ↓
[Frontend]   Créer les composants UI
    ↓
[Testing]    Rédiger et exécuter les tests
    ↓
[Documentation] Mettre à jour la doc
    ↓
[Review]     Valider le tout
```

### Règles de décomposition

- Une sous-tâche = un agent = une responsabilité
- Chaque sous-tâche a des inputs et outputs définis
- Les dépendances entre sous-tâches sont documentées
- Database (Supabase) est toujours avant Backend

## Validation

- [ ] Toutes les sous-tâches sont identifiées
- [ ] Les dépendances sont définies
- [ ] Chaque sous-tâche a un agent assigné

## Références

- `03-Orchestration/AGENT_ROUTER.md`
- `03-Orchestration/EXECUTION_PIPELINE.md`
