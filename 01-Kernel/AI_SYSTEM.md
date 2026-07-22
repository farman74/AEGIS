# AI SYSTEM

Version : 1.0
Status : Active

---

## Objectif

DEcrire l'architecture globale du système IA utilisé dans ExamOS.

## Quand utiliser

Premier document à lire après 00-Core. Définit le contexte système pour tout agent.

## Prérequis

- `00-Core/AI_MANIFESTO.md` lu.

## Procédure

### Vue globale

ExamOS utilise une architecture multi-agents :

```
Utilisateur
    ↓
[Agent Orchestrateur] ← 03-Orchestration
    ↓
[Agents Spécialistes]  ← 04-Agents
    ↓
[Services IA]          ← Supabase Edge Functions + LLM
    ↓
[Mémoire]             ← 02-Brain + Supabase
```

### Philosophie système

- Un agent = une responsabilité
- Pas de dépendances fortes entre agents
- Communication via contrats définis
- Tout résultat alimente le Brain

### Stack technique IA

- **Base de données** : Supabase (PostgreSQL managé)
- **Auth** : Supabase Auth
- **Storage** (copies, PDF, images) : Supabase Storage
- **Fonctions** : Supabase Edge Functions
- **Realtime** : Supabase Realtime
- **LLM** : Modèle défini dans 04-Agents/AI/

## Validation

- [ ] L'architecture multi-agents est comprise
- [ ] Les rôles sont identifiés
- [ ] Supabase est la seule base de données

## Références

- `01-Kernel/AI_ROLES.md`
- `03-Orchestration/`
- `04-Agents/`
