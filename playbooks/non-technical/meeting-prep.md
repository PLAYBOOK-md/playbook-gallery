# Meeting Preparation Brief

Prepare a structured brief so you walk into any meeting organized, confident, and ready to lead.

Nobody likes winging a meeting. This playbook takes your attendee list and agenda items and turns them into a polished preparation brief — complete with a timed agenda, talking points, smart questions, and a follow-up email draft. Works for everything from a quick standup to a board presentation.

## SYSTEM

You are an executive assistant and meeting strategist. You write clear, actionable briefs that help people run efficient meetings. Be concise and practical — no filler.

## INPUTS

- `meeting_type` (enum: sales call, board meeting, team standup, client review): Type of meeting
- `attendees` (text): List of attendees with their roles
- `agenda_items` (text): Topics to cover in the meeting
- `duration` (number: 30): Meeting length in minutes

## STEP 1: Analyze Context

Review the meeting details:

**Type:** {{meeting_type}}
**Duration:** {{duration}} minutes
**Attendees:** {{attendees}}
**Agenda:** {{agenda_items}}

Analyze and outline:
1. What each attendee likely cares about most, based on their role
2. Potential points of tension or disagreement
3. Decisions that need to be made during this meeting
4. Information you should have ready before walking in
5. The single most important outcome to achieve in {{duration}} minutes

## STEP 2: Create Timed Agenda

Build a structured agenda for this {{duration}}-minute {{meeting_type}} that covers all the agenda items:

{{agenda_items}}

For each agenda block, specify:
- **Time allocation** (e.g., 0:00-0:05)
- **Topic**
- **Owner** — who leads this section (pick from the attendees)
- **Goal** — what should be accomplished in this block
- **Format** — presentation, discussion, decision, or update

Include time for:
- A brief opening (1-2 minutes)
- A wrap-up with clear next steps (last 3-5 minutes)

Make sure the total adds up to exactly {{duration}} minutes.

## STEP 3: Prepare Talking Points

For each agenda item in this {{meeting_type}}, prepare:

1. **Key points to make** — the 2-3 things you want to communicate
2. **Supporting facts or data** — what backs up your points (suggest what to look up or prepare)
3. **Likely questions** — what attendees will probably ask, and how to answer
4. **Pivot phrases** — what to say if the conversation goes off track
5. **Decision framework** — if a decision is needed, how to frame the options clearly

Tailor the language and depth for a {{meeting_type}}. A board meeting needs different preparation than a team standup.

## STEP 4: Draft Follow-Up Email

Write a follow-up email template to send after this {{meeting_type}}.

The email should include:
- A brief summary of what was discussed
- Decisions that were made (with placeholders marked [decision] for filling in later)
- Action items in a clear list format: **Who** does **What** by **When**
- Any open questions that still need answers
- Date/time of next meeting or check-in (placeholder)

Keep it scannable — use bullet points and bold text. Attendees should be able to find their action items in under 10 seconds.

## ARTIFACTS

type: markdown
