# Objectif

Créer une nouvelle table dans Supabase pour ExamOS.

# Préconditions

- `05-Engineering/Database/RULES.md` lu
- Validation de l'agent Architecture reçue
- Supabase Dashboard accessible

# Étapes

1. **Définir le schéma** : nom de la table (snake_case pluriel), colonnes, types
2. **Vérifier les règles** :
   - UUID comme clé primaire (`id UUID DEFAULT gen_random_uuid() PRIMARY KEY`)
   - `organization_id UUID` si table métier
   - `created_at TIMESTAMPTZ DEFAULT NOW()`
   - `updated_at TIMESTAMPTZ DEFAULT NOW()`
   - `deleted_at TIMESTAMPTZ NULL` (soft delete)
3. **Écrire la migration SQL Supabase**
4. **Activer RLS** : `ALTER TABLE table_name ENABLE ROW LEVEL SECURITY;`
5. **Définir les RLS policies**
6. **Créer les index nécessaires**
7. **Documenter dans `02-Brain/`**

# Résultat attendu

Table créée dans Supabase avec RLS activé, soft delete implémenté et documentée.

# Validation finale

- [ ] Table créée dans Supabase
- [ ] UUID comme PK
- [ ] RLS activé et policies définies
- [ ] Soft delete présent
- [ ] Index créés
- [ ] Documenté dans Brain
- [ ] Checklist `09-Checklists/Database.md` validée
