# QUALITY STANDARD

Version : 1.0
Status : Active
Owner : AI CTO

---

## Objectif

Ce document définit les standards de qualité obligatoires pour tout élément produit dans ExamOS.

Ces standards s'appliquent à : Architecture, Code, Base de données (Supabase), API, IA, OCR, Sécurité, Documentation, Tests, UX, Performance, DevOps.

Aucune fonctionnalité ne peut être considérée comme terminée si ces standards ne sont pas respectés.

## Quand utiliser

Avant de soumettre tout livrable. Avant chaque revue. Avant chaque release.

## Prérequis

- `00-Core/ENGINEERING_PRINCIPLES.md` lu.

## Procédure

### Attributs de qualité

**Functional Correctness** : La fonctionnalité répond-elle exactement au besoin métier ?

**Reliability** : Le système continue-t-il à fonctionner en cas d'erreur (OCR partiel, réseau indisponible) ?

**Maintainability** : Le code est-il facile à modifier ? (faible couplage, forte cohésion)

**Scalability** : La fonctionnalité supporte-t-elle 10, 10 000, 1 000 000 de copies ?

**Security** : Les données sensibles sont protégées. Les permissions sont contrôlées.

**Explainability** : Toute décision IA est expliquée. Une note ne peut jamais être "attribuée par le modèle".

**Traceability** : Chaque correction enregistre : copie, modèle IA, version du prompt, version du barème, utilisateur, date, justification.

**Performance** : Chaque fonctionnalité possède des objectifs mesurables (temps, CPU, coût IA).

### Database Quality (Supabase)

Toute modification de la base de données Supabase doit respecter :
- Intégrité référentielle
- Migrations réversibles
- Index documentés
- Contraintes explicites
- Normalisation adaptée
- Auditabilité via Supabase Audit Logs

### Definition of Done

Une tâche est terminée uniquement si :
- [ ] Fonctionnalité conforme
- [ ] Tests réussis
- [ ] Documentation mise à jour
- [ ] Brain mis à jour
- [ ] Aucun bug bloquant
- [ ] Validation QA, Architecture, Sécurité, Performance

### Quality Gates

| Gate | Condition |
|---|---|
| Gate 1 — Product | Le besoin est valide |
| Gate 2 — Architecture | La solution est validée |
| Gate 3 — Development | Le code compile |
| Gate 4 — Review | La revue est approuvée |
| Gate 5 — QA | Les tests passent |
| Gate 6 — Documentation | Les documents sont synchronisés |
| Gate 7 — Release | La fonctionnalité peut être livrée |

## Validation

Tout livrable doit passer les 7 Quality Gates avant d'être considéré comme terminé.

## Références

- `00-Core/ENGINEERING_PRINCIPLES.md`
- `09-Checklists/`
- `02-Brain/`
