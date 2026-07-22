# Template — Prompt IA

## Objectif

Définir un prompt IA de manière uniforme, explicite et reproductible.

## Quand utiliser

À chaque fois qu'un prompt IA est créé ou modifié pour ExamOS.

## Prérequis

- Avoir lu `05-Engineering/AI/RULES.md`

## Procédure

---

```markdown
# Prompt — [Nom du prompt]

**Version :** 1.0  
**Modèle cible :** [GPT-4 | Claude | etc.]  
**Domaine :** [Correction | OCR | Analyse | etc.]  

---

## Contexte système (System Prompt)

[Décrire le rôle et le contexte donnés au modèle.]

## Instructions

[Instructions précises données au modèle.]

## Variables d'entrée

| Variable | Type | Description |
|---|---|---|
| `{question}` | string | L'intitulé de la question |
| `{student_answer}` | string | La réponse de l'élève |
| `{rubric}` | JSON | Le barème officiel |

## Format de sortie attendu

```json
{
  "score": 4,
  "max": 5,
  "confidence": 0.93,
  "comments": ["Bonne définition", "Exemple absent"]
}
```

## Exemples

**Entrée :**
[Exemple d'entrée]

**Sortie attendue :**
[Exemple de sortie]

## Comportements interdits

- [Comportement 1]
```

---

## Validation

Le prompt est validé après tests sur jeu de données réel.

## Références

- `05-Engineering/AI/RULES.md`
