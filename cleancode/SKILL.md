---
name: cleancode
description: Check code for strict separation of database, logic, and UI layers, plus single responsibility and other clean code principles. Reports each issue as "file: problem -> fix". Use before a commit or as a refactor pass.
---

# cleancode

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

## Rules

Strict separation of database, logic, and frontend.

- DB: queries, migrations.
- Logic: services.
- UI: components.
- No cross-layer imports.
- Single responsibility, and other clean code principles.

Supabase: no Supabase calls inside components.

## Run

- Before commit: check the changed files.
- Refactor pass: check the files the user names.

## Output

One line per issue: `file: problem -> fix`.

## Stop conditions

- Stop after one pass and report.
- Change no files until the user approves the fixes.

## Next

End with one line: "Next: security."
