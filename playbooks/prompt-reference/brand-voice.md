# Brand Voice Rewriter

Rewrite content to match a brand's voice and style guidelines by loading standards from a prompt library. Demonstrates the `@prompt` directive for pulling reusable prompts from external storage.

> **Note:** The `@prompt(library:id)` directive requires a configured prompt library or storage system. The executor must resolve the library reference to a stored prompt at runtime.

## SYSTEM

You are a content editor specializing in brand consistency. You ensure every piece of content aligns with established brand voice guidelines while preserving the original message and intent.

## INPUTS

- `content` (text): Content to rewrite in the brand voice
- `brand` (string: Acme Corp): Brand name to apply voice guidelines for

## STEP 1: Load Guidelines and Analyze

@prompt(library:brand-voice-guide)

Using the brand voice guidelines above for {{brand}}, analyze the following content and identify where it deviates from brand standards.

{{content}}

For each deviation, note:
1. The specific phrase or section
2. Which brand guideline it violates (tone, terminology, structure, etc.)
3. How severe the mismatch is (high / medium / low)

Respond with a JSON object:
{"deviation_count": 3, "overall_alignment": "low"}

@output(analysis, extract:"overall_alignment")

## STEP 2: Rewrite

Rewrite the content below to match {{brand}} brand voice guidelines. The current alignment level is {{analysis}}.

{{content}}

Follow these principles:
- Preserve the core message and all factual claims
- Apply brand-approved terminology and phrasing
- Match the brand's tone (formal/casual, authoritative/friendly, etc.)
- Maintain the original structure unless it conflicts with brand standards
- Ensure consistency from start to finish

@output(rewritten_content)

## STEP 3: Quality Check

Compare the rewritten content against the original and the brand guidelines:

1. **Message preservation**: Does the rewrite keep every key point from the original?
2. **Voice consistency**: Does the tone match {{brand}} guidelines throughout?
3. **Terminology**: Are all brand-specific terms used correctly?
4. **Readability**: Is the rewrite clear and natural (not forced or robotic)?

If any issues remain, fix them and output the final version.

## ARTIFACTS

type: markdown
