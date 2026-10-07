# my-skills

Personal Claude skills. Concise, readable, stack-aware.

## Skills

| Skill | What it does |
| --- | --- |
| prd | Scope, then write a PRD. |
| db-plan | Plan a database schema. |
| backend-plan | Plan a backend structure. |
| test-design | Decide what to test, at which level, and why. |
| hot-mess | Find inconsistencies and unify them. |
| ubermansk | Build in a loop: plan, build, test, fix. Manual only: `/ubermansk`. |
| cleancode | Check layer separation and clean code. |
| security | Security check on staged changes. |
| idontgetit | Explain a repo. Read-only. |

Flow: prd -> db-plan -> backend-plan -> test-design -> ubermansk -> cleancode -> security -> commit. Each skill also works standalone.

## Install

Claude Code only finds skills at `~/.claude/skills/<name>/SKILL.md`, so link each folder there. `_shared` must be linked too.

PowerShell, from the repo root:

```powershell
Get-ChildItem -Directory | ForEach-Object {
  New-Item -ItemType Junction -Path "$HOME\.claude\skills\$($_.Name)" -Target $_.FullName
}
```

Edits in the repo apply at once. Rerun after adding a new skill.

## Shared files

- `_shared/style.md`: output rules every skill follows.
- `_shared/stack.md`: default stack and how skills pick the stack.
