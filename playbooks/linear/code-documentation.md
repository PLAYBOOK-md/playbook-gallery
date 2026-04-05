# Code Documentation Generator

Analyze source code and produce comprehensive documentation with usage examples.

## INPUTS

- `code` (text): Source code to document
- `language` (string: Go): Programming language
- `audience` (enum: internal, public-api, onboarding): Documentation audience

## STEP 1: Analyze

Analyze this {{language}} code and identify:

{{code}}

1. All public functions/methods with their signatures
2. Data types and their relationships
3. Key algorithms or patterns used
4. External dependencies
5. Error handling approach

## STEP 2: Document

Write documentation for a {{audience}} audience.

For each public function/method, include:
- Purpose (one sentence)
- Parameters with types and descriptions
- Return value
- Error conditions
- Thread safety or concurrency notes (if relevant)

## STEP 3: Examples

Generate 2-3 realistic usage examples that demonstrate:
1. Basic usage (the common case)
2. Error handling (what can go wrong)
3. An advanced pattern (if the API supports it)

Use idiomatic {{language}} style.

## ARTIFACTS

type: markdown
