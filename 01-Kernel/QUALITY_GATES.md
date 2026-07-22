# QUALITY GATES

Version : 1.0
Status : Active

---

## Objectif

Définir les contrôles de qualité obligatoires à chaque étape du cycle de développement.

## Quand utiliser

Avant de considérer une étape comme terminée.

## Procédure

### Les 7 Gates

**Gate 1 — Product**
- [ ] Le besoin est validé par le propriétaire du produit
- [ ] Les critères d'acceptation sont définis

**Gate 2 — Architecture**
- [ ] La solution est conforme à l'architecture AEGIS
- [ ] Aucune base de données autre que Supabase
- [ ] ADR créé si décision architecturale

**Gate 3 — Development**
- [ ] Le code compile sans erreur
- [ ] Les conventions de nommage sont respectées
- [ ] Aucun code mort

**Gate 4 — Review**
- [ ] La revue est approuvée
- [ ] Aucune violation de principe

**Gate 5 — QA**
- [ ] Tests unitaires passés
- [ ] Tests d'intégration passés
- [ ] Tests métier passés

**Gate 6 — Documentation**
- [ ] Documentation mise à jour dans la même PR
- [ ] Brain mis à jour

**Gate 7 — Release**
- [ ] Tous les gates précédents validés
- [ ] Validation finale

## Validation

Aucune fonctionnalité ne contourne un Quality Gate.

## Références

- `00-Core/QUALITY_STANDARD.md`
- `09-Checklists/`
