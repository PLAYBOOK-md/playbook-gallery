# Playbook Gallery

A curated collection of [PLAYBOOK.md](https://github.com/PLAYBOOK-MD/playbook-spec) playbooks demonstrating real-world AI workflow patterns.

## Playbooks

### Linear Pipelines

Simple multi-step chains — no branching, no directives beyond the basics.

| Playbook | Steps | Description |
|----------|-------|-------------|
| [Content Pipeline](playbooks/linear/content-pipeline.md) | 4 | Research, outline, draft, polish |
| [Meeting Notes](playbooks/linear/meeting-notes.md) | 3 | Transcribe, summarize, extract action items |
| [Code Documentation](playbooks/linear/code-documentation.md) | 3 | Analyze, document, generate examples |
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
