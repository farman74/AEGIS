# PROJECT CONSTITUTION

Version : 1.0
Status : Active
Owner : AI CTO

---

## Objectif

Ce document est la loi fondamentale du projet ExamOS.

Il définit :
- ce qu'est le projet
- ce qu'il n'est pas
- ses valeurs fondamentales
- ses contraintes absolues
- les règles non-négociables

Tout agent (humain ou IA) travaillant sur ExamOS doit lire et respecter ce document.

## Quand utiliser

Lire ce document :
- avant de démarrer une nouvelle tâche
- avant de prendre une décision architecturale
- en cas de doute sur la direction du projet

## Prérequis

Aucun. C'est le premier document à lire.

## Procédure

---

### 1. Identité du projet

**Nom** : ExamOS
**Categorie** : AI-Powered Examination Management Platform
**Objectif** : Devenir le système d'exploitation des examens académiques.

ExamOS couvre l'intégralité du cycle d'un examen :
- Création du sujet
- Gestion des candidats et centres
- Numérisation des copies
- Assistance à la correction par IA
- Validation humaine
- Publication des résultats
- Gestion des recours
- Statistiques et archivage

### 2. Ce que ExamOS n'est PAS

- Un chatbot
- Un logiciel de notes
- Une plateforme de QCM
- Un LMS
- Un ERP scolaire classique

ExamOS est un **Workflow Engine** pour les examens, dans lequel l'IA est un service parmi d'autres.

### 3. Valeurs fondamentales

**Humain responsable** : L'IA assiste. L'humain décide. Toujours.

**Transparence** : Chaque point attribué doit être explicable.

**Traçabilité** : Chaque décision est historisée.

**Modularité** : L'IA est un composant. Le système fonctionne même si elle est remplacée.

**Auditabilité** : Toute correction peut être vérifiée des années après.

### 4. Contraintes absolues

- Base de données : **Supabase uniquement**. Aucune autre option.
- Architecture : **Figée**. Toute modification nécessite un ADR.
- Documentation : **Synchronisée**. Aucun code sans doc.
- AEGIS : **Source de vérité**. Aucune règle en dehors d'AEGIS.

### 5. Règles non-négociables

- Une IA ne peut jamais inventer une règle métier.
- Une IA ne peut jamais modifier l'architecture sans ADR.
- Une IA ne peut jamais ignorer les règles de sécurité.
- Une IA ne peut jamais créer de duplication.

## Validation

Ce document est validé par le propriétaire du projet.
Toute modification nécessite un ADR dans `02-Brain/`.

## Références

- `00-Core/ENGINEERING_PRINCIPLES.md`
- `00-Core/QUALITY_STANDARD.md`
- `00-Core/AI_MANIFESTO.md`
- `02-Brain/` (décisions et ADR)
