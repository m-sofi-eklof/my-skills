---
name: db-plan
description: Plan a database schema. Asks scale, auth, and hosting first, then outputs a table or diagram plus open questions. Use when the user wants to design or plan a database, schema, or data model.
---

# db-plan

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

Ask before planning, one at a time. Skip any the stack file or a PRD already answers.

1. Scale
2. Auth
3. Hosting

## Output

- Table or diagram of the schema.
- Open questions.
- Save where the repo keeps its plans. If nowhere, save to `docs/db-plan.md`.

## Supabase

If the stack is Supabase, also cover:

- RLS policies
- Migrations
- Generated types

## Next

End with one line: "Next: backend-plan."
