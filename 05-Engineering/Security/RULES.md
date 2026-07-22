# Règles Sécurité

## Objectif

Règles de sécurité obligatoires pour ExamOS.

## Procédure

### Règles fondamentales

1. **Supabase Auth** : Toute authentification passe par Supabase Auth.
2. **RLS** : Row Level Security activé sur toutes les tables sensibles.
3. **RBAC** : Les rôles sont définis et appliqués via Supabase + tables de rôles.
4. **HTTPS** : Obligatoire sur toutes les communications.
5. **Chiffrement** : Stockage chiffré via Supabase Storage.
6. **Audit** : Toute action sensible est loggée dans `audit_logs`.
7. **Anonymisation** : Le correcteur voit l'identifiant copie, pas le nom du candidat.
8. **Secrets** : Variables d'environnement Supabase, jamais en dur.

### Rôles ExamOS

| Rôle | Droits |
|---|---|
| SUPER_ADMIN | Accès total |
| MINISTRY_ADMIN | Gestion au niveau ministère |
| SCHOOL_ADMIN | Gestion établissement |
| CORRECTOR | Voir et corriger ses copies assignées |
| STUDENT | Voir ses propres résultats |

## Validation

- [ ] Supabase Auth activé
- [ ] RLS configuré
- [ ] HTTPS actif
- [ ] Audit logs actifs

## Références

- `04-Agents/Security/`
- `09-Checklists/Security.md`
