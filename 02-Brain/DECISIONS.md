# DECISIONS — Décisions prises

Mis à jour : 2026-07-22

---

Ce document liste toutes les décisions techniques importantes prises sur le projet ExamOS.

Pour les décisions architecturales majeures, un ADR est disponible dans `02-Brain/ADR/`.

---

## Décisions actives

### DEC-001 — Base de données : Supabase

**Date** : 2026-07-22
**Statut** : Définitif
**ADR** : `02-Brain/ADR/ADR-001-supabase.md`
**Décision** : ExamOS utilise exclusivement Supabase comme système de persistance.
Toute référence à PostgreSQL local, SQLite, Firebase, MongoDB ou Prisma est obsolète et interdite.

### DEC-002 — Architecture documentaire : AEGIS

**Date** : 2026-07-22
**Statut** : Définitif
**Décision** : Le framework documentaire AEGIS est la source de vérité unique.
L'architecture à 13 dossiers (00-Core à 12-Automation + README) est figée.
Aucun autre dossier n'est autorisé.

### DEC-003 — Philosophie IA-First

**Date** : 2026-07-22
**Statut** : Définitif
**Décision** : Tous les documents AEGIS sont rédigés pour être lus par des agents IA.
La structure de chaque document est standardisée pour minimiser l'ambigüité.

### DEC-004 — ExamOS comme Workflow Engine

**Date** : 2026-07-22
**Statut** : Définitif
**Décision** : ExamOS n'est pas une simple IA de correction.
C'est un Workflow Engine pour la gestion complète des examens académiques.
L'IA est un service parmi d'autres.
