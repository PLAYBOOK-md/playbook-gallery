# Multi-Audience Tone Adapter

Take a piece of content and adapt it for different audiences with appropriate tone, depth, and terminology.

## INPUTS

- `content` (text): Original content to adapt
- `target` (enum: executive, technical, general-public): Target audience
- `max_length` (number: 500): Maximum word count for adapted version

## STEP 1: Analyze Source

Analyze the following content and identify:

{{content}}

1. Core message (one sentence)
2. Key facts and data points
3. Technical terms that may need translation
4. Assumptions about reader knowledge

@output(core_message, extract:"core_message")

## STEP 2: Adapt

```if target == "executive"```

### STEP 2a: Executive Summary

Rewrite for a C-suite audience in under {{max_length}} words:
- Lead with business impact and ROI
- Replace technical jargon with business language
- Include a clear recommendation or call to action
- Use bullet points for scanability

```elif target == "technical"```

### STEP 2b: Technical Deep Dive

Rewrite for a technical audience in under {{max_length}} words:
- Preserve all technical detail and terminology
- Add implementation context where helpful
- Include relevant metrics, benchmarks, or specifications
- Reference standards or best practices

```else```

### STEP 2c: General Public Version

Rewrite for a general audience in under {{max_length}} words:
- Use plain language (no jargon)
- Explain concepts with analogies
- Focus on "why it matters" over "how it works"
- Keep sentences short and paragraphs brief

```endif```

## STEP 3: Quality Check

Review the adapted version and:
1. Verify the core message is preserved
2. Confirm it stays under {{max_length}} words
3. Check that tone is consistent throughout
4. Flag any remaining jargon inappropriate for the {{target}} audience

Output the final polished version.

## ARTIFACTS

type: markdown
