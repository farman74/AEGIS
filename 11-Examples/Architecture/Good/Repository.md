# Bon Exemple — Repository Pattern

## Objectif

Montrer un bon exemple d'implémentation du pattern Repository dans ExamOS.

## Quand utiliser

Référencer cet exemple lors de la création d'un nouveau Repository.

## Exemple

```typescript
// GOOD — Repository abstrait, injecté, testable
export class ExamRepository {
  constructor(private readonly supabase: SupabaseClient) {}

  async findById(id: string): Promise<Exam | null> {
    const { data, error } = await this.supabase
      .from('exams')
      .select('*')
      .eq('id', id)
      .single();
    if (error) throw new RepositoryError(error.message);
    return data;
  }

  async create(exam: CreateExamDto): Promise<Exam> {
    const { data, error } = await this.supabase
      .from('exams')
      .insert(exam)
      .select()
      .single();
    if (error) throw new RepositoryError(error.message);
    return data;
  }
}
```

## Pourquoi c'est bon

- Utilise Supabase exclusivement
- Abstraction claire
- Erreurs gérées explicitement
- Testable via injection de dépendances
- Une responsabilité unique

## Références

- `05-Engineering/Architecture/BEST_PRACTICES.md`
- `08-Patterns/Architecture/`
