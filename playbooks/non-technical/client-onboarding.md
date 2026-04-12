# Client Onboarding Email Sequence

Create a warm, professional series of emails to welcome a new client and keep them engaged throughout their onboarding period.

This playbook helps service-based businesses make a great first impression. It takes basic details about the client and service, then produces a complete email sequence — from the initial welcome through check-ins — so nothing falls through the cracks.

## SYSTEM

You are a friendly, professional business communications writer. Write emails that feel personal and warm, not corporate or templated. Use clear, simple language and keep paragraphs short.

## INPUTS

- `client_name` (string): Name of the new client
- `service` (string): The service or package the client signed up for
- `timeline` (enum: 1 week, 2 weeks, 1 month): Expected onboarding duration

## STEP 1: Analyze Service Details

Review the service details for {{client_name}}:

**Service:** {{service}}
**Onboarding timeline:** {{timeline}}

Identify:
1. What the client likely expects in their first few days
2. Key milestones they should hit during the {{timeline}} onboarding period
3. Common questions new clients have about this type of service
4. Moments where they might feel uncertain or need reassurance

## STEP 2: Draft Welcome Email

Write a welcome email for {{client_name}} that:

- Opens with a warm, genuine greeting (not "Dear Valued Client")
- Confirms what they signed up for: {{service}}
- Sets clear expectations for the {{timeline}} ahead
- Lists 2-3 immediate next steps they should take
- Includes your availability and how to reach you
- Closes with enthusiasm about working together

Keep it under 300 words. It should feel like it came from a real person, not a CRM system.

## STEP 3: Create Follow-Up Sequence

Create a sequence of follow-up emails spaced across the {{timeline}} onboarding period for {{client_name}}.

For each email, provide:
- **When to send** (e.g., Day 3, End of Week 1)
- **Subject line**
- **Full email body**
- **Purpose** (what this email accomplishes)

The sequence should:
- Check in on their progress with {{service}}
- Share a helpful tip or resource at each touchpoint
- Ask a specific question to encourage a reply
- Gradually build confidence that they made the right choice

Write 3-4 follow-up emails depending on the {{timeline}} length.

## STEP 4: Write Check-In Template

Write a reusable check-in email template for ongoing use after the onboarding period ends.

The template should:
- Work for monthly or quarterly check-ins with {{client_name}}
- Include placeholder spots marked with [brackets] for specific updates
- Ask about their satisfaction with {{service}}
- Open the door for upsells or referrals in a natural, non-pushy way
- Be adaptable — easy to personalize in under 2 minutes

## ARTIFACTS

type: markdown
