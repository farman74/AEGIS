# DecisionTrees — Database

## Objectif

Arbres de décision pour les choix de base de données dans ExamOS.

## Décisions couvertes

### Décision principale : Quelle base de données ?

```
Quelle base utiliser pour ExamOS ?
    ↓
    Supabase
    (Décision définitive — ADR-001)
```

Cette décision est **définitive**. Voir `02-Brain/ADR/ADR-001-supabase.md`.

### Décision : Stocker un fichier volumineux ?

```
Fichier > 1MB ou binaire ?
    ↓ Oui
    Utiliser Supabase Storage
    ↓ Non
    Stocker en colonne TEXT ou BYTEA dans Supabase Database
```

### Décision : Table métier ou table système ?

```
La table contient-elle des données multi-tenant ?
    ↓ Oui
    Ajouter organization_id + activer RLS
    ↓ Non
    Table système standard
```

## Liens

- `02-Brain/ADR/ADR-001-supabase.md`
- `05-Engineering/Database/RULES.md`
