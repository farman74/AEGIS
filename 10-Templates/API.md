# Template — Documentation API

## Objectif

Documenter un endpoint API de manière uniforme et complète.

## Quand utiliser

À chaque fois qu'un nouvel endpoint est créé ou modifié.

## Prérequis

- Avoir lu `05-Engineering/API/RULES.md`

## Procédure

---

```markdown
# API — [Nom de l'endpoint]

**Méthode :** GET | POST | PUT | PATCH | DELETE  
**URL :** `/api/v1/[resource]`  
**Auth :** Requis | Non requis  
**Permission :** [Rôle requis]  

---

## Description

[Décrire ce que fait cet endpoint.]

## Paramètres

| Nom | Type | Requis | Description |
|---|---|---|---|
| `param1` | string | Oui | ... |

## Corps de la requête (si applicable)

```json
{
  "field": "value"
}
```

## Réponse succès

**Code :** 200 | 201  
**Corps :**
```json
{
  "data": {}
}
```

## Erreurs possibles

| Code | Message | Cause |
|---|---|---|
| 401 | Unauthorized | Token manquant |
| 403 | Forbidden | Permission insuffisante |
| 422 | Validation Error | Champ invalide |

## Exemple

```bash
curl -X POST /api/v1/resource \
  -H "Authorization: Bearer TOKEN" \
  -d '{"field":"value"}'
```
```

---

## Validation

L'endpoint est validé lorsque la documentation est synchronisée avec le code.

## Références

- `05-Engineering/API/RULES.md`
