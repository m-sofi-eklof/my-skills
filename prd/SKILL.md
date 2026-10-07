---
name: prd
description: Write a PRD in two phases. Scope first as bullets, then write the document. Use when the user wants a PRD, product spec, or to scope a feature before building.
---

# prd

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

## Phase 1: scope

- Bullets only. Simple and concise.
- Touch no files.
- Move to phase 2 only when the user approves the scope.

## Phase 2: write

- Write the PRD from the approved scope.
- If the repo has a PRD template, follow it exactly.
- If not, use the default: Problem, Goals, Scope, Out of scope, Open questions.
- Save where the repo keeps its PRDs. If nowhere, save to `docs/prd.md`.

## Hard rule

If anything comes up that wasn't pre-planned, stop and ask one short question before writing more.

## Decisions log

- Keep a decisions log so nothing is silently invented.
- Log every decision the user makes.
- Put it where the repo keeps its decisions. If nowhere, add a "Decisions" section at the end of the PRD.

## Next

End with one line: "Next: db-plan."
