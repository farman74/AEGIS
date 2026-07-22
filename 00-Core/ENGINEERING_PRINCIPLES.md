# ENGINEERING PRINCIPLES

Version : 1.0
Status : Active
Owner : AI CTO

---

## Objectif

Ce document définit les 20 principes fondamentaux qui gouvernent toutes les décisions techniques prises dans ExamOS.

Ces principes sont obligatoires pour tous : développeurs, IA, reviewers, architectes.

Aucune exception n'est autorisée sans ADR.

## Quand utiliser

Avant chaque décision technique. Avant chaque revue. En cas de doute.

## Prérequis

- `00-Core/PROJECT_CONSTITUTION.md` lu et compris.

---

## Procédure

### Principle 1 — Business First
La logique métier est plus importante que la technologie.
Toujours commencer par comprendre le besoin, les utilisateurs, les règles et les contraintes avant de penser au code.

### Principle 2 — Architecture before Implementation
Une fonctionnalité ne doit jamais commencer par du code.
Ordre obligatoire : Business → Architecture → Contrats → Implémentation → Tests → Documentation.

### Principle 3 — Single Source of Truth
Une information ne doit exister qu'à un seul endroit. Aucune duplication.

### Principle 4 — Explicit over Implicit
Les comportements cachés sont interdits. Les noms, dépendances et permissions doivent être explicites.

### Principle 5 — Modularity
Chaque module doit pouvoir évoluer indépendamment.

### Principle 6 — Loose Coupling
Les modules communiquent via interfaces, événements, contrats ou services. Jamais via des dépendances fortes.

### Principle 7 — High Cohesion
Toutes les responsabilités d'un module doivent être liées entre elles.

### Principle 8 — Domain Driven Design
Le métier pilote l'architecture. Le code reflète les concepts métier (Exam, Paper, Correction, Rubric…) et non des concepts techniques.

### Principle 9 — Feature Driven Development
On développe des fonctionnalités, pas des couches techniques isolées. Chaque tâche apporte une valeur métier.

### Principle 10 — Atomic Changes
Une Pull Request = un objectif. Une tâche = une responsabilité.

### Principle 11 — Explainability
Chaque décision IA doit pouvoir être expliquée : pourquoi, quelle règle, quel extrait du barème, quel raisonnement.

### Principle 12 — Traceability
Toute action doit être traçable : qui, quand, pourquoi, version IA, version barème.

### Principle 13 — Reproducibility
Une correction doit pouvoir être reproduite. Mêmes données = même résultat.

### Principle 14 — Security by Design
La sécurité est présente dès la conception. Jamais ajoutée à la fin.

### Principle 15 — Privacy by Design
Les données des candidats sont sensibles. Minimiser l'exposition, le stockage et la duplication.

### Principle 16 — AI Assisted, Human Controlled
L'IA assiste. Le système décide. L'humain valide lorsque le processus l'exige.

### Principle 17 — Testability
Toute fonctionnalité doit être testable. Si elle ne peut pas être testée, l'architecture est probablement mauvaise.

### Principle 18 — Observability
Tout incident doit être observable. Logs, métriques, tracing, audit.

### Principle 19 — Performance Budget
Chaque fonctionnalité possède un coût (CPU, RAM, stockage, temps de réponse, coût IA). Ce coût doit rester maîtrisé.

### Principle 20 — Continuous Documentation
Le code évolue, la documentation évolue. Aucune fonctionnalité ne peut être fusionnée sans mise à jour de sa documentation.

---

## Comportements interdits pour toute IA

- Inventer une règle métier
- Modifier l'architecture sans ADR
- Créer de la duplication
- Ignorer les contraintes métier
- Coder plusieurs fonctionnalités dans une même tâche
- Supprimer une documentation officielle
- Ignorer les performances, la sécurité ou les tests

## Validation

Checklist avant développement :
- [ ] Le besoin est compris
- [ ] Les règles métier sont connues
- [ ] Le contexte est chargé
- [ ] Les dépendances sont identifiées
- [ ] Les risques sont connus
- [ ] Les critères d'acceptation sont définis

## Références

- `00-Core/PROJECT_CONSTITUTION.md`
- `00-Core/QUALITY_STANDARD.md`
- `02-Brain/` (ADR)
