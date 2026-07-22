# REVIEW PIPELINE

Version : 1.0
Status : Active

---

## Objectif

Définir qui valide, quand refaire une tâche et quand arrêter.

## Quand utiliser

Étape 5 du pipeline d'exécution.

## Procédure

### Qui valide

| Type de livrable | Validateur |
|---|---|
| Décision architecturale | Architecte + Humain |
| Code Backend (Supabase) | Agent Review + Testing |
| Code Frontend | Agent Review + Testing |
| Modification schéma Supabase | Database + Architecte |
| Documentation | Documentation + Review |
| Prompt IA | AI + Review |

### Quand refaire

- Règle métier violée
- Architecture modifiée sans ADR
- Sécurité compromise
- Documentation absente
- Tests absents
- Supabase non respecté

### Quand arrêter

Quand tous les Quality Gates de `01-Kernel/QUALITY_GATES.md` sont passés.

## Validation

- [ ] Le validateur approprié a été identifié
- [ ] Tous les Quality Gates sont passés

## Références

- `01-Kernel/REVIEW_PROTOCOL.md`
- `01-Kernel/QUALITY_GATES.md`
- `09-Checklists/Review.md`
