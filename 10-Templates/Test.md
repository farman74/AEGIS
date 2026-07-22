# Template — Test

## Objectif

Définir un cas de test de manière uniforme et reproductible.

## Quand utiliser

À chaque création d'un test unitaire, d'intégration ou métier.

## Prérequis

- Avoir lu `05-Engineering/Testing/RULES.md`

## Procédure

---

```markdown
# Test — [Nom du test]

**Type :** Unitaire | Intégration | Métier | Performance  
**Module :** [Nom du module]  
**Priorité :** Critique | Haute | Normale  

---

## Objectif

[Décrire ce que ce test valide.]

## Préconditions

- [Condition 1]

## Données d'entrée

```json
{
  "input": "value"
}
```

## Étapes

1. [Etape 1]
2. [Etape 2]

## Résultat attendu

```json
{
  "output": "expected"
}
```

## Cas limites couverts

- [Cas 1]

## Résultat observé

[ ] Passant  [ ] Échouant
```

---

## Validation

Le test est validé lorsqu'il couvre tous les cas limites définis.

## Références

- `05-Engineering/Testing/RULES.md`
- `09-Checklists/Testing.md`
