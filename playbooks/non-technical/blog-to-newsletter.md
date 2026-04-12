# Blog Post to Newsletter Converter

Transform a blog post into a newsletter your subscribers will actually open and read.

Blog posts and newsletters are different formats with different reader expectations. A blog visitor chose to click; a newsletter subscriber is giving you inbox space. This playbook takes your existing blog content and reshapes it for email — adjusting the tone, length, structure, and adding the subject lines and CTAs that drive engagement.

## INPUTS

- `blog_post` (text): The full blog post content to convert
- `newsletter_style` (enum: digest, deep-dive, tips): Newsletter format style
- `subscriber_count` (number: 1000): Approximate number of subscribers
- `include_cta` (boolean: true): Whether to include a call-to-action section

## STEP 1: Extract Key Points

Read the following blog post and pull out what matters most:

{{blog_post}}

Identify:
1. **Main takeaway** — the single most valuable idea for readers
2. **Supporting points** — 3-5 key facts, insights, or arguments
3. **Quotable moments** — any lines that would work well as standalone highlights
4. **Links and resources** — anything worth linking to in the newsletter
5. **Reader benefit** — what does someone gain by reading this?

Also assess the original tone and reading level. Note what needs to change for a {{newsletter_style}}-style newsletter.

## STEP 2: Adapt for Newsletter

Rewrite the content from the blog post as a {{newsletter_style}}-style newsletter.

```if newsletter_style == "digest"```

### STEP 2a: Digest Format

Structure as a quick-scan digest:
- **TL;DR** at the top — 2-3 sentences covering the main point
- **Bullet-point summary** of key insights (5-7 bullets max)
- **One highlighted quote or stat** that stands out
- **Link to full post** for readers who want more detail

Keep it under 300 words. Digest readers want speed — respect their time.

```elif newsletter_style == "deep-dive"```

### STEP 2b: Deep-Dive Format

Restructure as an in-depth newsletter essay:
- **Personal opening** — a brief anecdote or observation that connects to the topic
- **Core content** — the main ideas rewritten in a conversational, first-person tone
- **Added context** — expand on one point that deserves more attention than the blog gave it
- **Takeaway section** — what the reader should do with this information

Target 600-800 words. Deep-dive readers chose this format because they want substance.

```else```

### STEP 2c: Tips Format

Repackage as actionable tips:
- **Opening hook** — one sentence about why these tips matter right now
- **Numbered tips** (3-5) — each with a clear action the reader can take today
- **Quick win** — highlight the one tip that takes under 5 minutes
- **Resource link** — point to the full blog post for background

Keep it under 400 words. Tips readers want to do something, not just read something.

```endif```

Adapt the language for an audience of roughly {{subscriber_count}} subscribers. A 500-person list feels intimate; a 50,000-person list needs broader appeal.

## STEP 3: Write Subject Lines and Preview Text

Create email subject line and preview text options for this newsletter.

Provide:
- **5 subject line options** — varied styles (curiosity, benefit, urgency, question, direct)
- **Preview text** for each — the snippet that appears after the subject line in the inbox
- **A/B test recommendation** — which 2 subject lines to test and why

Guidelines:
- Keep subject lines under 50 characters when possible
- Preview text should complement the subject line, not repeat it
- Avoid spam trigger words (free, act now, limited time)
- Write for the {{newsletter_style}} reader — match their expectations

## STEP 4: Write Call-to-Action

```if include_cta```

Write a call-to-action section to close the newsletter.

Create 3 CTA options, each with a different goal:
1. **Drive traffic** — get readers to visit the full blog post or website
2. **Start a conversation** — encourage replies or social shares
3. **Grow the list** — ask readers to forward the newsletter to someone who would benefit

For each CTA:
- Write the exact copy (2-3 sentences)
- Suggest button text if applicable
- Explain when to use this option

The CTAs should feel natural at the end of a {{newsletter_style}} newsletter, not like a jarring sales pitch.

```else```

Write a brief, warm sign-off for the newsletter. Keep it to 1-2 sentences. End on a note that makes readers look forward to the next issue — no sales pitch, no ask, just a good closing.

```endif```

## ARTIFACTS

type: markdown
