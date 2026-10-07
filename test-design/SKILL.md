---
name: test-design
description: Design a test plan. Decides the test levels first (unit only, or unit + integration + e2e), then outputs what to test, at which level, and why. Use when the user wants to plan tests, a test strategy, or test coverage.
---

# test-design

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

## First decision

Ask before anything else: "Unit only, or unit + integration + e2e?"

## Output

One table: what to test | level | why.

Save where the repo keeps its plans. If nowhere, save to `docs/test-design.md`.

## Next

End with one line: "Next: ubermansk."
