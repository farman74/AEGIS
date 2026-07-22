# Template — Pull Request

## Objectif

Uniformiser la description des Pull Requests pour faciliter la revue humaine et IA.

## Quand utiliser

À chaque création de Pull Request dans le projet.

## Prérequis

- La checklist de domaine concernée doit être validée avant ouverture de la PR.

## Procédure

---

```markdown
## Description

[Décrire en une phrase l'objectif de cette PR.]

## Type de changement

- [ ] Nouvelle fonctionnalité
- [ ] Correction de bug
- [ ] Refactoring
- [ ] Documentation
- [ ] Migration base de données (Supabase)

## Changements effectués

- [Changement 1]
- [Changement 2]

## Tests

- [ ] Tests unitaires ajoutés
- [ ] Tests d'intégration ajoutés
- [ ] Tests passants

## Checklists validées

- [ ] `09-Checklists/Backend.md`
- [ ] `09-Checklists/Testing.md`
- [ ] `09-Checklists/Documentation.md`

## Documentation mise à jour

- [ ] Oui
- [ ] Non applicable

## Brain mis à jour

- [ ] Oui
- [ ] Non applicable
```

---

## Validation

La PR est prête à la revue lorsque toutes les cases sont cochées.

## Références

- `09-Checklists/Review.md`
- `03-Orchestration/REVIEW_PIPELINE.md`
