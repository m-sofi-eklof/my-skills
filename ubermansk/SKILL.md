---
name: ubermansk
description: Build fast in an agentic loop of plan, build, run tests, fix, repeat. Has a max iteration count and stops to ask on unplanned decisions, repeated failures, or scope changes. Use when the user wants a feature built autonomously, or invokes /ubermänsk.
disable-model-invocation: true
---

# ubermänsk

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

## Loop

1. Plan
2. Build
3. Run tests
4. Fix
5. Repeat

Use these if they exist. Look where the repo keeps its plans, otherwise:

- `docs/prd.md`
- `docs/db-plan.md`
- `docs/backend-plan.md`
- `docs/test-design.md`

## Stop conditions

- Tests pass and the plan is done: stop and report.
- Max iterations reached: stop and report. Default 5, unless the user gives another number.

## Stop and ask

Stop and ask one short question when:

- A decision comes up that wasn't planned.
- The same test fails 3 times in a row.
- The scope changes.

## Report

When stopping: what was built, what passes, what is left.

## Next

End with one line: "Next: cleancode."
