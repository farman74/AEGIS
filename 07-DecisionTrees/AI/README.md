# DecisionTrees — IA

## Décisions couvertes

### OCR local ou cloud ?

```
Volume > 10 000 copies/jour ?
    ↓ Oui
    OCR cloud (scalable)
    ↓ Non
    OCR local ou cloud selon coût — ADR nécessaire
```

### Cache réponse IA ?

```
Même copie + même barème + même version modèle ?
    ↓ Oui
    Cache Supabase (réduction coût IA)
    ↓ Non
    Appel IA direct
```

## Liens

- `05-Engineering/AI/RULES.md`
