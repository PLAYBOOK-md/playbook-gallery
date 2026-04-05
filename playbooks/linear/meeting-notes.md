# Meeting Notes Processor

Transform raw meeting notes or a transcript into structured, actionable output.

## INPUTS

- `transcript` (text): Raw meeting notes or transcript
- `team` (string: Engineering): Team name for context

## STEP 1: Summarize

Summarize the following meeting notes for the {{team}} team.

{{transcript}}

Provide:
1. Meeting purpose (one sentence)
2. Key discussion points (3-5 bullets)
3. Decisions made

## STEP 2: Action Items

Extract all action items from the meeting. For each action item, identify:

- **Owner**: Who is responsible (use names from the transcript, or "TBD")
- **Task**: What needs to be done
- **Deadline**: If mentioned, otherwise "Not specified"
- **Priority**: High / Medium / Low based on discussion urgency

Format as a table.

## STEP 3: Follow-up Email

Draft a brief follow-up email to the {{team}} team with:
1. One-paragraph summary
2. Action items table
3. Next meeting date (if mentioned)

Keep the tone professional but friendly.

## ARTIFACTS

type: markdown
