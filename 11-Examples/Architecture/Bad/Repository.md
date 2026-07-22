# Mauvais Exemple — Repository Pattern

## Objectif

Montrer un mauvais exemple d'implémentation du pattern Repository à éviter absolument.

## Quand utiliser

Référencer cet exemple pour éviter les anti-patterns courants.

## Exemple

```typescript
// BAD — Accès direct, couplage fort, non testable
class ExamController {
  async getExam(id: string) {
    // INTERDIT : connexion directe à une base locale
    const db = new PrismaClient(); // ❌ Prisma interdit
    const exam = await db.exam.findUnique({ where: { id } });
    return exam; // ❌ Retour de modèle brut sans transformation
  }
}
```

## Pourquoi c'est mauvais

- Utilise Prisma au lieu de Supabase (✖ interdit)
- Logique de base de données dans le Controller
- Couplage fort, impossible à tester
- Retourne un modèle brut sans API Resource
- Aucune gestion d'erreur

## Références

- `05-Engineering/Architecture/ANTI_PATTERNS.md`
