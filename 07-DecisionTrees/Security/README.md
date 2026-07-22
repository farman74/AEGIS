# DecisionTrees — Sécurité

## Décisions couvertes

### Quelle méthode d'authentification ?

```
Toujours : Supabase Auth
(Décision définitive — ADR-001)
```

### RLS nécessaire ?

```
Table contient des données utilisateur ou sensibles ?
    ↓ Oui
    RLS obligatoire
    ↓ Non
    RLS recommandé mais non obligatoire
```

## Liens

- `05-Engineering/Security/RULES.md`
