---
name: security
description: Security check on staged changes before a commit. Covers secrets, input validation, auth, dependencies, SQL injection, XSS, CORS, rate limiting, and Supabase RLS and keys. Reports each issue as "file: risk -> fix". Use before committing.
---

# security

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

Runs before commit, on staged changes only.

1. Map out the checklist against the staged changes.
2. Check each item.
3. Always run the package manager's audit (e.g. `npm audit`), even if no lockfile is staged.
4. Report.

## Checklist

- Secrets in code
- Input validation
- Auth / authorization
- Dependency vulnerabilities
- SQL injection
- XSS
- CORS
- Rate limiting

Supabase:

- RLS checks
- Service-role key leaks
- Anon key scope

## Output

One line per issue: `file: risk -> fix`.

## Stop conditions

- Stop after one pass over the staged changes and report.
- Change no files until the user approves the fixes.

## Next

End with one line: "Next: commit."
