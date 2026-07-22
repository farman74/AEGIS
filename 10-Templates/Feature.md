# Template — Feature Contract

## Objectif

Définir formellement le contrat d'une fonctionnalité avant tout développement.
Empêche une IA de partir dans la mauvaise direction.

## Quand utiliser

Avant de démarrer le développement de toute nouvelle fonctionnalité.

## Prérequis

- Avoir lu `00-Core/ENGINEERING_PRINCIPLES.md`
- Le besoin métier doit être validé par l'humain.

## Procédure

---

```markdown
# Feature Contract — [Nom de la fonctionnalité]

**Version :** 1.0  
**Statut :** Brouillon | Validé | En cours | Terminé  
**Owner :** [Rôle]  

---

## Objectifs métier

[Décrire ce que cette fonctionnalité apporte à l'utilisateur.]

## Règles métier

1. [Règle 1]
2. [Règle 2]

## Écrans concernés

- [Page ou composant 1]
- [Page ou composant 2]

## API

- `POST /api/v1/[resource]` — [description]

## Permissions

| Rôle | Peut lire | Peut écrire | Peut supprimer |
|---|---|---|---|
| Admin | Oui | Oui | Oui |
| Correcteur | Oui | Non | Non |

## Modèles IA utilisés

- [Modèle 1] — [Usage]

## Tests obligatoires

- [ ] [Test 1]
- [ ] [Test 2]

## Risques

- [Risque 1]

## KPI

- [Métrique 1] : cible [valeur]

## Definition of Done

- [ ] Fonctionnalité conforme aux règles métier
- [ ] Tests réussis
- [ ] Documentation mise à jour
- [ ] Brain mis à jour
- [ ] Validation humaine
```

---

## Validation

Le Feature Contract est validé lorsque l'humain l'a approuvé avant le début du développement.

## Références

- `00-Core/ENGINEERING_PRINCIPLES.md`
- `09-Checklists/Review.md`
