# Routine-ready playbooks

Playbooks in this directory are designed to run autonomously as [Claude Code Routines](https://code.claude.com/docs/en/routines) — no `@elicit`, no breakpoints, structured inputs with defaults where appropriate.

See the full guide at [docs.playbook.style/guides/claude-code-routines](https://docs.playbook.style/guides/claude-code-routines/) for the zero-code setup recipe.

## Playbooks

| Playbook | Trigger fit | Description |
|----------|-------------|-------------|
| [Weekly Docs Drift](weekly-docs-drift.md) | Schedule (weekly) | Scan merged PRs, flag stale docs, produce a prioritized update list |

## Running one

Copy the playbook to your repo at `./playbooks/<name>.playbook.md`, commit the [`playbook-run` skill](https://github.com/PLAYBOOK-MD/playbook-integrations/blob/main/skills/playbook-run/SKILL.md) into `.claude/skills/playbook-run/SKILL.md`, and create a routine at [claude.ai/code/routines](https://claude.ai/code/routines) pointing at the playbook.
