# PLAYBOOK.md Gallery

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub stars](https://img.shields.io/github/stars/PLAYBOOK-MD/playbook-gallery)](https://github.com/PLAYBOOK-MD/playbook-gallery/stargazers)

A curated collection of [PLAYBOOK.md](https://github.com/PLAYBOOK-MD/playbook-spec) playbooks demonstrating real-world AI workflow patterns.

## Playbooks

### Claude Code Routines

Playbooks designed for autonomous, scheduled or triggered [Claude Code Routines](https://code.claude.com/docs/en/routines). No elicitation or breakpoints; structured inputs with defaults.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Weekly Docs Drift](playbooks/routines/weekly-docs-drift.md) | 4 | Scan merged PRs, flag stale docs, produce prioritized update list |

### Ready for GitHub Actions

Playbooks that run as-is on [`PLAYBOOK-MD/playbook-native`](https://github.com/PLAYBOOK-MD/playbook-native) (standalone Node runtime for `.playbook.md` files in CI). Any playbook without `@tool(…)`, `@prompt(mcp:…)`, or `@prompt(library:…)` directives is native-compatible; the table below highlights ones that pair naturally with common GitHub Actions triggers.

| Playbook | Trigger shape | Notes |
|----------|---------------|-------|
| [Weekly Docs Drift](playbooks/routines/weekly-docs-drift.md) | `schedule` (cron) | Same shape as the routines listing — runs here too |
| [Content Pipeline](playbooks/linear/content-pipeline.md) | `workflow_dispatch` | Pass `topic`, `audience`, `word_count` as dispatch inputs |
| [API Schema Generator](playbooks/linear/api-schema.md) | `workflow_dispatch` | Typed inputs + JSON artifact |

### Linear Pipelines

Simple multi-step chains — no branching, no directives beyond the basics.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Content Pipeline](playbooks/linear/content-pipeline.md) | 4 | Research, outline, draft, polish |
| [Meeting Notes](playbooks/linear/meeting-notes.md) | 3 | Transcribe, summarize, extract action items |
| [Code Documentation](playbooks/linear/code-documentation.md) | 3 | Analyze, document, generate examples |
| [API Schema Generator](playbooks/linear/api-schema.md) | 3 | Generate JSON/GraphQL API schemas (`type: json` artifact, `boolean` input) |
| [Security Review](playbooks/linear/security-review.md) | 3 | `@prompt`-driven security review with library criteria |

### Branching Workflows

Conditional execution based on inputs or AI-generated classifications.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Adaptive Code Review](playbooks/branching/adaptive-review.md) | 2 | Review focus adapts to selected mode |
| [Issue Triage](playbooks/branching/issue-triage.md) | 2 | Classify issues, route to appropriate workflow |
| [Tone Adapter](playbooks/branching/tone-adapter.md) | 3 | Adapt content for different audiences |

### Human-in-the-Loop

Workflows with elicitation checkpoints for human review and input.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Decision Matrix](playbooks/human-in-the-loop/decision-matrix.md) | 5 | Technology evaluation with review gates |
| [Iterative Draft](playbooks/human-in-the-loop/iterative-draft.md) | 4 | Draft, review, revise cycle |

### Tool Integration

Playbooks that invoke external tools via `@tool` directives.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Data Analysis](playbooks/tool-integration/data-analysis.md) | 3 | Fetch data, analyze, report |

### Prompt Reference

Playbooks that use `@prompt` to load reusable prompts from an external library.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Brand Voice Rewriter](playbooks/prompt-reference/brand-voice.md) | 3 | Load brand guidelines via `@prompt(library:id)`, then rewrite content to match |

### Non-Technical

Playbooks for product managers, marketers, creators, and small business owners — no dev jargon required.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Client Onboarding](playbooks/non-technical/client-onboarding.md) | 4 | Welcome email, follow-up sequence, and check-in template |
| [Social Media Campaign](playbooks/non-technical/social-media-campaign.md) | 4 | Audience research, content calendar, post drafts, engagement templates |
| [Meeting Prep](playbooks/non-technical/meeting-prep.md) | 4 | Context analysis, timed agenda, talking points, follow-up email |
| [Product Launch Checklist](playbooks/non-technical/product-launch-checklist.md) | 4 | Positioning, budget-adapted checklist, launch day timeline, measurement plan |
| [Blog to Newsletter](playbooks/non-technical/blog-to-newsletter.md) | 4 | Extract key points, adapt format, subject lines, call-to-action (`boolean` input) |

## Ready for Claude Code Routines

These playbooks run well as [Claude Code Routines](https://code.claude.com/docs/en/routines) — autonomous, scheduled or triggered Claude Code sessions. All avoid `@elicit` (which cannot pause an autonomous run) or can be adapted using the [elicit-defaults convention](https://docs.playbook.style/guides/claude-code-routines/#elicit-in-autonomous-runs).

Full setup guide: [Run Playbooks as Claude Code Routines](https://docs.playbook.style/guides/claude-code-routines/).

| Playbook | Category | Typical trigger |
|----------|----------|-----------------|
| [Weekly Docs Drift](playbooks/routines/weekly-docs-drift.md) | Routines | Schedule (weekly) |
| [Content Pipeline](playbooks/linear/content-pipeline.md) | Linear | Schedule or API |
| [Issue Triage](playbooks/branching/issue-triage.md) | Branching | GitHub (issues.opened) |
| [Meeting Notes](playbooks/linear/meeting-notes.md) | Linear | API (post-meeting upload) |
| [Code Documentation](playbooks/linear/code-documentation.md) | Linear | GitHub (push to main) |
| [API Schema Generator](playbooks/linear/api-schema.md) | Linear | Schedule |
| [Adaptive Code Review](playbooks/branching/adaptive-review.md) | Branching | GitHub (pull_request.opened) |
| [Tone Adapter](playbooks/branching/tone-adapter.md) | Branching | API |

## Contributing

We welcome community-contributed playbooks. To submit:

1. Fork this repo
2. Add your playbook to the appropriate category directory
3. Update this README with an entry in the table
4. Open a PR

### Guidelines

- Playbooks must be valid PLAYBOOK.md format (see the [spec](https://github.com/PLAYBOOK-MD/playbook-spec))
- Include a clear title and description
- Use realistic, practical workflows (not toy examples)
- Keep playbooks self-contained — avoid external dependencies where possible

## License

All playbooks in this gallery are licensed under [CC BY 4.0](LICENSE).
