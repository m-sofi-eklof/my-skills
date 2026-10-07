---
name: hot-mess
description: Find inconsistencies across a project and unify them. Walks the whole project, reports one table of what differs, and asks which version is the single truth before changing anything. Use when the user wants a project cleanup, unification, or consistency pass.
---

# hot-mess

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

## Run

1. Walk the full project.
2. Find inconsistencies: the same thing done in different ways.
3. Report the table.
4. For each row, ask which version is the single truth. One question at a time.
5. Apply only the fixes the user approved.

## Output

One table: area | what differs | recommended fix.

More detail only if asked.

## Stop conditions

- Stop after one full walkthrough and report the table.
- Change no files until the user picks the single truth for that row.
