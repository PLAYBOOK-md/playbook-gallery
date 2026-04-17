# Weekly Docs Drift Report

Scan merged PRs from the last 7 days, flag documentation that references changed APIs, and produce a prioritized update list.

Designed to run as a weekly Claude Code Routine — no elicitation, no breakpoints, no human-in-the-loop.

## SYSTEM

You are a documentation maintainer. Be precise — cite exact file paths and PR numbers. Prefer conservative flags (false-positive-tolerant) over missing real drift. When in doubt, flag it.

## INPUTS

- `repo_path` (string: .): Path to the repository root (default: current directory)
- `days` (number: 7): Look-back window in days
- `docs_root` (string: docs): Path to the documentation root relative to repo_path
- `severity_threshold` (enum: low, medium, high): Minimum drift severity to report

## STEP 1: Collect Recent Changes

Run `git log --since="{{days}} days ago" --merges --pretty=format:"%H|%s|%an|%ad"` in `{{repo_path}}` and list the merged PRs. For each merged PR, capture:
- PR number (extract from commit subject, e.g. "Merge pull request #123")
- Commit SHA
- Subject line
- Files changed (via `git show --name-only --pretty="" <sha>`)

Return a structured JSON array:
```json
[{"pr": 123, "sha": "abc123", "subject": "...", "files": ["src/api/users.ts", "..."]}]
```

@output(recent_changes: json)

## STEP 2: Identify API-Touching Changes

From the changes above, classify each PR by whether it plausibly changed an API surface:

- Check if files changed are in typical API locations: `src/api/`, `src/routes/`, `src/handlers/`, `openapi.yaml`, `schema.graphql`, exported interfaces, etc.
- For each API-touching PR, list the specific surface touched (endpoint path, function signature, type name).

Respond with a JSON object:
```json
{"api_changes": [{"pr": 123, "surface": "GET /users/:id"}]}
```

@output(api_changes: json, extract:"api_changes")

## STEP 3: Scan Docs for References

```if severity_threshold == "high"```

### STEP 3a: High-Severity Only

For each API surface in `api_changes`, grep the {{docs_root}} tree for direct references (endpoint strings, function names, type names). Flag a doc file only if it contains a literal reference and the PR body/diff suggests a breaking change (added/removed/renamed). Skip additive changes.

@output(drift_report)

```elif severity_threshold == "medium"```

### STEP 3b: Medium-Severity

For each API surface, grep the {{docs_root}} tree. Flag doc files that reference the surface, unless the change is purely internal (e.g. implementation refactor with no external signature change).

@output(drift_report)

```else```

### STEP 3c: All Drift

Grep the {{docs_root}} tree for any reference to any changed surface. Include even minor drift (comment-only changes, typo fixes in API examples).

@output(drift_report)

```endif```

## STEP 4: Write Report

Produce a markdown report with:

1. **Summary line** — "N docs drift items found over the last {{days}} days, severity >= {{severity_threshold}}"
2. **Per-item sections** — for each flagged doc:
   - Doc file path
   - Which PR caused the drift
   - What the doc currently says (verbatim excerpt)
   - Suggested correction (concise)
3. **Tail** — list of PRs reviewed with no drift (so the maintainer knows they were checked)

Format as GitHub-Flavored Markdown with collapsible sections for long excerpts.

## ARTIFACTS

type: markdown
