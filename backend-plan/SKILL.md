---
name: backend-plan
description: Plan a backend structure. Asks scale, auth, and hosting first, then outputs flows, logic, entities, services, integrations, and entry points as tables or diagrams, plus open questions. Use when the user wants to design or plan a backend, API, or service architecture.
---

# backend-plan

## Style

- Short and easy to read. Fewest words that work.
- Problem: "X is a problem because Y." Fix: "I can fix it, but I need X."
- Choice: "Choose between A (pros: ..., cons: ...) and B (pros: ..., cons: ...)."
- One short question at a time. Extra explanation only when asked.

If `${CLAUDE_SKILL_DIR}/../_shared/style.md` exists, it wins. If not, the rules above are enough.

## Project rules

If the project has its own rules for saving files, follow them. They win over this skill.

## Stack

1. Check for `.claude/stack.md` in the project. If it exists, use it.
2. If not, ask: "Default stack (TS + Supabase) or custom?"
3. If custom: ask language, framework, DB, hosting once. Save to `.claude/stack.md`.

If `${CLAUDE_SKILL_DIR}/../_shared/stack.md` exists, it wins. If not, the steps above are enough.

## Ask first

Ask before planning, one at a time. Skip any the stack file, a PRD, or a db-plan already answers.

1. Scale
2. Auth
3. Hosting

## Output

Short tables or diagrams per section. One line per item.

1. Flows: main user and data flows, step by step.
2. Logic: business rules and where each one lives.
3. DB entities: tables, key columns, relations. Reuse the db-plan if one exists.
4. Services and their functions: one line each.
5. External clients / integrations: what, where used.
6. Entry points: routes, edge functions, jobs.
7. Other as relevant: auth, env vars, config.
8. Open questions.

Save where the repo keeps its plans. If nowhere, save to `docs/backend-plan.md`.

## Supabase

If the stack is Supabase, also cover:

- Edge Functions: which ones, what each does.
- Auth: how users sign in, where it is checked.
- RLS: which rules live in policies, which in code.

## Next

End with one line: "Next: test-design."
