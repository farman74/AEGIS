# Patterns — Database (Supabase)

## Objectif

Patterns de base de données recommandés pour ExamOS avec Supabase.

## Patterns disponibles

### Pattern : Multi-Tenant avec Supabase

**Description** : Architecture multi-tenant via `organization_id` + RLS.

**Quand l'utiliser** : Toute table m��tier partagée entre plusieurs organisations.

**Quand ne pas l'utiliser** : Tables système globales (ex : liste des pays).

**Avantages** : Isolation des données, scalable, natif Supabase.

**Inconvénients** : Requires RLS policy sur chaque table.

**Exemple** :
```sql
CREATE TABLE exams (
    id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
    organization_id UUID NOT NULL REFERENCES organizations(id),
    name TEXT NOT NULL,
    created_at TIMESTAMPTZ DEFAULT NOW(),
    deleted_at TIMESTAMPTZ NULL
);
ALTER TABLE exams ENABLE ROW LEVEL SECURITY;
```

### Pattern : Stockage de fichiers avec Supabase Storage

**Description** : Stocker les fichiers volumineux (copies, PDF) dans Supabase Storage, garder uniquement l'URL dans la base.

**Exemple** :
```sql
CREATE TABLE scan_files (
    id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
    storage_path TEXT NOT NULL, -- chemin dans Supabase Storage
    file_name TEXT NOT NULL,
    created_at TIMESTAMPTZ DEFAULT NOW()
);
```

## Liens

- `05-Engineering/Database/RULES.md`
- `07-DecisionTrees/Database/README.md`
