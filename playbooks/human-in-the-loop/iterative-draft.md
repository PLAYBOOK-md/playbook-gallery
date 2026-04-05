# Iterative Draft with Feedback

Write, review, and revise content with a human feedback loop.

## INPUTS

- `brief` (text): Writing brief or requirements
- `format` (enum: blog post, report, email, documentation): Content format
- `tone` (string: professional): Desired tone

## STEP 1: First Draft

Write a {{format}} based on the following brief:

{{brief}}

Use a {{tone}} tone. Focus on getting the structure and key points right.

## STEP 2: Self-Review

Review your draft above and provide:
1. Three strengths of the current draft
2. Three specific areas that need improvement
3. Any gaps in coverage relative to the brief

@output(self_review)

## STEP 3: Get Feedback

@elicit(input, "Review the draft and self-assessment above. What changes would you like? Be specific about what to keep, cut, or revise.")
@output(feedback)

## STEP 4: Final Revision

Revise the draft incorporating the feedback: {{feedback}}

Also address the self-identified improvements from the review.

Produce the final {{format}} ready for publication.

## ARTIFACTS

type: markdown
