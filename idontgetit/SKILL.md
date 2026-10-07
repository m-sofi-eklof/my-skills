---
name: idontgetit
description: Explain a repo in simple categories (DB entities, services, integrations, entry points). Read-only, never changes code. Accepts an optional focus such as "only the billing part". Use when the user wants to understand a codebase or says they don't get it.
disallowed-tools: Write, Edit, NotebookEdit
---

# idontgetit

## Style

- Short and easy to read. Fewest words that work.
- Problem: "X is a problem because Y." Fix: "I can fix it, but I need X."
- Choice: "Choose between A (pros: ..., cons: ...) and B (pros: ..., cons: ...)."
- One short question at a time. Extra explanation only when asked.

If `${CLAUDE_SKILL_DIR}/../_shared/style.md` exists, it wins. If not, the rules above are enough.

## Project rules

If the project has its own rules for saving files, follow them. They win over this skill.

## Stack

- If `.claude/stack.md` exists in the project, use it.
- If not, read the stack from the repo. Never ask, never save.

## Rules

- Read-only. Never change code.
- Optional focus: if the user gives one ("only the billing part"), cover only that.

## Output

Start with a 3-line overview. Then short tables or lists per category. One line per item.

1. DB entities: tables, key columns, relations.
2. Services and their functions: one line each.
3. External clients / integrations: what, where used.
4. Entry points: routes, edge functions, jobs.
5. Other as relevant: auth, env vars, config.

Deeper detail on one item only if asked.

## Stop conditions

- Stop after one pass and report.
