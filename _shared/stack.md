# Stack

## Default

- Language: TypeScript, JavaScript
- Backend: Supabase (Postgres, Auth, RLS, Edge Functions)

## Behaviour

1. Check for `.claude/stack.md` in the project.
2. If it exists: use it, skip the question.
3. If not: ask "Default stack (TS + Supabase) or custom?"
4. If custom: ask language, framework, DB, hosting once. Save to `.claude/stack.md`.

Tradeoff: asked once per project (pro), but the file can go stale (con).

## Where stack matters most

- db-plan: RLS policies, migrations, generated types.
- security: RLS checks, service-role key leaks, anon key scope.
- cleancode: layers are DB (queries/migrations), logic (services), UI (components). No Supabase calls inside components.
