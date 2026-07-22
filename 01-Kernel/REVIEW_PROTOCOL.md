# REVIEW PROTOCOL

Version : 1.0
Status : Active

---

## Objectif

Définir comment effectuer une revue de qualité sur un livrable.

## Quand utiliser

Après chaque tâche, avant de soumettre un livrable.

## Procédure

### Questions de revue

1. Le besoin est-il compris et couvert ?
2. L'architecture est-elle respectée ?
3. Le code est-il simple et lisible ?
4. Existe-t-il de la duplication ?
5. Les erreurs sont-elles correctement gérées ?
6. Les performances sont-elles acceptables ?
7. La documentation est-elle complète ?
8. Les tests sont-ils définis ?
9. Supabase est-il correctement utilisé ?
10. Les risques sont-ils identifiés ?

### Quand refaire une tâche

- Si une règle métier est violée
- Si l'architecture est modifiée sans ADR
- Si la sécurité est compromise
- Si la documentation est absente
- Si les tests sont absents

### Quand arrêter

N'arrêter que lorsque tous les Quality Gates sont passés (`00-Core/QUALITY_STANDARD.md`).

## Validation

- [ ] Les 10 questions de revue ont été répondues
- [ ] Tous les Quality Gates sont passés

## Références

- `00-Core/QUALITY_STANDARD.md`
- `09-Checklists/Review.md`
- `03-Orchestration/REVIEW_PIPELINE.md`
