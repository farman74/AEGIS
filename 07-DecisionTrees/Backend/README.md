# DecisionTrees — Backend

## Décisions couvertes

### REST ou GraphQL ?

```
Nombre de clients différents ?
    ↓ 1-2 clients
    REST API (simple, prévisible)
    ↓ Nombreux clients avec besoins différents
    GraphQL à considérer (ADR nécessaire)
```

### Logique synchrone ou asynchrone ?

```
Tâche longue (OCR, correction IA, batch) ?
    ↓ Oui
    Architecture asynchrone (Supabase Edge Functions + queue)
    ↓ Non
    Traitement synchrone
```

## Liens

- `05-Engineering/Backend/RULES.md`
