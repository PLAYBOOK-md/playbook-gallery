# Security Code Review

Run a structured security review against a stored review criteria prompt, then produce a findings report.

## SYSTEM

You are a senior application security engineer specializing in OWASP Top 10, secure coding practices, and threat modeling.

## INPUTS

- `code` (text): Source code to review
- `language` (string: Go): Programming language
- `scope` (enum: full, auth-only, data-flow): Review scope

## STEP 1: Apply Review Criteria

@prompt(library:owasp-review-criteria)

Apply the review criteria above to the following {{language}} code. Focus on {{scope}} analysis.

{{code}}

Respond with a JSON object:
{"severity": "critical", "finding_count": 3}

@output(findings, extract:"severity")

## STEP 2: Deep Dive

Based on the initial findings (severity: {{findings}}), provide a detailed breakdown:

1. For each vulnerability found, describe the attack vector
2. Provide a concrete fix with code example
3. Rate exploitability (low/medium/high)

@output(details)

## STEP 3: Executive Summary

Write a one-page security review summary suitable for a team lead:
- Overall risk assessment based on {{findings}} severity level
- Top 3 issues requiring immediate action
- Recommended remediation timeline

## ARTIFACTS

type: markdown
