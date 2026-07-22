# AEGIS
## AI-Governed Engineering Intelligence System

> Framework documentaire IA-First pour le développement d'ExamOS.  
> Version : 2.0 — Conforme aux nouvelles normes officielles  
> Status : Active  
> Owner : AI CTO

---

## Philosophie

AEGIS est un framework documentaire conçu pour permettre à n'importe quel agent IA (Cursor, Claude Code, Codex, Copilot…) de développer ExamOS de manière cohérente, sans halluciner les règles métier, sans casser l'architecture et sans perdre le contexte.

L'idée centrale est simple :  
**Une IA ne peut bien travailler que si elle dispose d'un contexte parfaitement structuré.**

AEGIS fournit ce contexte. Pas le code. Pas la logique. Uniquement les règles, les protocoles et les standards.

### Principes fondateurs
- **IA-First** : Chaque document est rédigé pour être lu et interprété par une IA avant tout.
- **Single Source of Truth** : Chaque information n'existe qu'à un seul endroit.
- **Zero Ambiguity** : Aucune décision ne peut être arbitraire. Tout est documenté.
- **Human Controlled** : L'IA assiste. L'humain valide.
- **Supabase-Native** : Toute la persistance des données repose sur Supabase (PostgreSQL managé).

---

## Architecture Officielle

L'architecture AEGIS est **figée**. Elle ne peut être modifiée que par une décision formelle documentée dans un ADR.

```
AEGIS/
│
├── 00-Core/            ← Identité, principes, qualité, manifeste IA
├── 01-Kernel/          ← Protocoles IA (mémoire, contexte, tâches, review…)
├── 02-Brain/           ← Mémoire vivante du projet (décisions, ADR, état)
│
├── 03-Orchestration/   ← Pipeline unique : routing, planification, exécution
├── 04-Agents/          ← Spécialistes IA par domaine
├── 05-Engineering/     ← Règles techniques par domaine
├── 06-Playbooks/       ← Protocoles pas-à-pas pour chaque tâche récurrente
├── 07-DecisionTrees/   ← Arbres de décision pour supprimer les choix arbitraires
├── 08-Patterns/        ← Architectures recommandées par domaine
├── 09-Checklists/      ← Listes de vérification avant validation
├── 10-Templates/       ← Modèles officiels de documents et livrables
├── 11-Examples/        ← Bons et mauvais exemples par domaine
├── 12-Automation/      ← Automatisations standardisées
│
└── README.md           ← Ce fichier (point d'entrée unique)
```

**Aucun autre dossier n'est autorisé.**

---

## Workflow Global

Le flux d'une demande est **strictement ordonné** et ne change jamais :

```
Utilisateur
    ↓
03-Orchestration    (analyse, routage, planification)
    ↓
04-Agents           (exécution par spécialiste)
    ↓
06-Playbooks        (protocole pas-à-pas)
    ↓
05-Engineering      (règles techniques)
    ↓
08-Patterns         (architectures recommandées)
    ↓
07-DecisionTrees    (choix guidés)
    ↓
09-Checklists       (vérification)
    ↓
10-Templates        (livrables uniformes)
    ↓
11-Examples         (références)
    ↓
12-Automation       (automatisation)
    ↓
02-Brain            (mise à jour mémoire)
```

---

## Rôle de chaque dossier

### 00-Core — Identité du projet
Contient les documents fondateurs qui définissent ce qu'est AEGIS, ses valeurs et ses standards non-négociables.

| Fichier | Rôle |
|---|---|
| `PROJECT_CONSTITUTION.md` | La loi fondamentale du projet |
| `ENGINEERING_PRINCIPLES.md` | Les 20 principes d'ingénierie obligatoires |
| `QUALITY_STANDARD.md` | Les standards de qualité pour chaque livrable |
| `AI_MANIFESTO.md` | Les règles de comportement de toute IA travaillant sur le projet |

### 01-Kernel — Protocoles IA
Contient les protocoles que toute IA doit suivre pour interagir avec le projet.

| Fichier | Rôle |
|---|---|
| `AI_SYSTEM.md` | Description du système IA global |
| `AI_ROLES.md` | Rôles et responsabilités de chaque IA |
| `MEMORY_PROTOCOL.md` | Comment mémoriser et rappeler le contexte |
| `CONTEXT_PROTOCOL.md` | Quels documents lire, dans quel ordre |
| `TASK_PROTOCOL.md` | Comment traiter une tâche |
| `REVIEW_PROTOCOL.md` | Comment effectuer une revue |
| `DECISION_PROTOCOL.md` | Comment prendre une décision technique |
| `COMMUNICATION_PROTOCOL.md` | Comment communiquer avec l'humain |
| `QUALITY_GATES.md` | Les gates de qualité obligatoires |

### 02-Brain — Mémoire vivante
Contient l'état actuel du projet : décisions prises, ADR, progression, contexte persistant.

### 03-Orchestration — Pipeline unique
Chaque demande passe par ce pipeline. Aucune exception.

| Fichier | Rôle |
|---|---|
| `AGENT_ROUTER.md` | Quel agent utiliser, dans quel ordre |
| `TASK_PLANNER.md` | Décomposition des grosses demandes |
| `EXECUTION_PIPELINE.md` | Cycle complet d'exécution |
| `CONTEXT_MANAGER.md` | Gestion du contexte documentaire |
| `REVIEW_PIPELINE.md` | Qui valide, quand et comment |

### 04-Agents — Spécialistes IA
Un agent par domaine. Chaque agent a exactement la même structure interne :
`README.md` / `MISSION.md` / `RESPONSIBILITIES.md` / `WORKFLOW.md` / `INPUTS.md` / `OUTPUTS.md` / `CHECKLIST.md`

Domaines : `Architecture/` `Backend/` `Database/` `Frontend/` `OCR/` `AI/` `Security/` `Testing/` `Documentation/` `Review/`

### 05-Engineering — Règles techniques
Règles techniques par domaine. Aucune logique. Uniquement les standards.

Chaque module contient : `README.md` / `RULES.md` / `BEST_PRACTICES.md` / `ANTI_PATTERNS.md` / `TESTING.md`

Domaines : `Architecture/` `Backend/` `Database/` `Frontend/` `OCR/` `AI/` `Security/` `API/` `Performance/` `Testing/`

### 06-Playbooks — Protocoles de tâches
Un playbook = une tâche récurrente. Chaque playbook suit le modèle :
`Objectif` → `Préconditions` → `Étapes` → `Résultat attendu` → `Validation finale`

### 07-DecisionTrees — Choix guidés
Un arbre = une décision. Exemples : Quel type de base ? REST ou GraphQL ? OCR local ou cloud ?

### 08-Patterns — Architectures recommandées
Chaque pattern contient : `Description` / `Quand l'utiliser` / `Quand ne pas l'utiliser` / `Avantages` / `Inconvénients` / `Exemple`

### 09-Checklists — Vérification
Une checklist par domaine. Une IA doit valider la checklist avant de soumettre un livrable.

Fichiers : `Architecture.md` `Backend.md` `Frontend.md` `Database.md` `OCR.md` `Security.md` `Testing.md` `Documentation.md` `Review.md`

### 10-Templates — Modèles officiels
Modèles uniformes pour tous les livrables.

Fichiers : `ADR.md` `API.md` `Feature.md` `Prompt.md` `PR.md` `Issue.md` `Test.md` `Documentation.md`

### 11-Examples — Références concrètes
Bons et mauvais exemples par domaine. Chaque dossier contient `Good/` et `Bad/`.

### 12-Automation — Automatisations standardisées
Chaque automatisation suit : `Déclencheur` → `Étapes` → `Résultat` → `Mise à jour Brain`

Fichiers : `NEW_FEATURE.md` `BUG_FIX.md` `CODE_REVIEW.md` `DOCUMENTATION_UPDATE.md` `RELEASE.md`

---

## Base de données — Supabase

**ExamOS utilise exclusivement Supabase** comme système de persistance.

- Backend : Supabase (PostgreSQL managé)
- Auth : Supabase Auth
- Storage : Supabase Storage (copies scannées, PDF, images)
- Realtime : Supabase Realtime (notifications, suivi en temps réel)
- Edge Functions : Supabase Edge Functions (logique serverless légère)

Toute référence à PostgreSQL local, SQLite, Firebase, MongoDB, Prisma ou tout autre système de base de données est **interdite** et doit être considérée comme obsolète.

---

## Conventions documentaires

### Standard README de chaque dossier
```
# Objectif
# Structure
# Comment utiliser
# Liens avec les autres dossiers
```

### Standard des documents internes
```
# Objectif
# Quand utiliser
# Prérequis
# Procédure
# Validation
# Références
```

---

## Règles de contribution

1. **Lire AEGIS avant de travailler.** Commencer par `00-Core/`, puis `01-Kernel/`, puis `02-Brain/`.
2. **Ne jamais inventer une règle.** Si une règle n'est pas dans AEGIS, elle n'existe pas.
3. **Mettre à jour le Brain** après chaque décision importante.
4. **Respecter les templates.** Tout document produit doit respecter le template officiel correspondant.
5. **Un ADR par décision architecturale.** Toute déviation de l'architecture nécessite un ADR.
6. **Supabase uniquement.** Aucune autre base de données n'est autorisée.

---

## Projet associé : ExamOS

AEGIS est le framework de gouvernance du projet **ExamOS** — une plateforme AI-Powered de gestion des examens académiques.

ExamOS ambitionne de devenir le système d'exploitation des examens : de la création du sujet jusqu'à l'archivage des résultats, en passant par la numérisation, la correction IA, la validation humaine et la publication.

---

## Démarrage rapide pour une IA

```
1. Lire README.md (ce fichier)
2. Lire 00-Core/PROJECT_CONSTITUTION.md
3. Lire 00-Core/ENGINEERING_PRINCIPLES.md
4. Lire 01-Kernel/CONTEXT_PROTOCOL.md
5. Lire 02-Brain/ (état actuel du projet)
6. Consulter 03-Orchestration/AGENT_ROUTER.md
7. Exécuter la tâche selon le Playbook correspondant dans 06-Playbooks/
8. Mettre à jour 02-Brain/ en fin de session
```

---

*AEGIS — Construit pour durer. Conçu pour les IA. Validé par les humains.*
