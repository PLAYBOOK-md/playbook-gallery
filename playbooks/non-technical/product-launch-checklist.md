# Product Launch Checklist

Build a complete launch plan tailored to your product, market, and budget — from pre-launch prep through post-launch measurement.

Launching a product is stressful, and it is easy to miss critical steps. This playbook produces a structured checklist and timeline adapted to your budget level. A bootstrap launch looks very different from an enterprise one, and the branching logic here handles that automatically.

## SYSTEM

You are a product marketing strategist who has helped launch products at every scale — from solo founder side projects to enterprise SaaS rollouts. Give practical, specific advice. Skip the theory and focus on what to actually do.

## INPUTS

- `product_name` (string): Name of the product being launched
- `launch_date` (string): Target launch date
- `target_market` (text): Description of the target market and ideal customer
- `budget_level` (enum: bootstrap, moderate, enterprise): Available budget for the launch

## STEP 1: Analyze Market and Positioning

Analyze the launch context for {{product_name}}:

**Launch date:** {{launch_date}}
**Target market:** {{target_market}}
**Budget level:** {{budget_level}}

Develop:
1. A one-sentence positioning statement for {{product_name}}
2. The top 3 pain points this product solves for the target market
3. Key differentiators from likely competitors
4. The primary and secondary channels to reach this audience
5. A realistic goal for launch day (sign-ups, sales, downloads, or awareness)

## STEP 2: Build Pre-Launch Checklist

Create a detailed pre-launch checklist for {{product_name}} leading up to {{launch_date}}.

```if budget_level == "bootstrap"```

### STEP 2a: Bootstrap Launch Checklist

Focus on high-impact, zero-cost or low-cost tactics:

- **Landing page** — what to include and free tools to build it
- **Email list** — how to build a waitlist with no ad spend
- **Social proof** — getting early testimonials from beta users or friends
- **Content** — 3-5 pieces of organic content to publish before launch
- **Communities** — specific communities, forums, or groups to engage with
- **Personal network** — how to mobilize your existing contacts
- **Product Hunt / launch platforms** — preparation steps and timeline

Organize as a week-by-week checklist leading up to {{launch_date}}.

```elif budget_level == "moderate"```

### STEP 2b: Moderate Budget Launch Checklist

Balance organic and paid strategies:

- **Landing page and ads** — page optimization plus a small paid campaign plan
- **Email marketing** — list building with lead magnets and a nurture sequence
- **Influencer outreach** — how to partner with 3-5 micro-influencers affordably
- **PR** — writing and distributing a press release on a budget
- **Content marketing** — blog posts, guest posts, and social content calendar
- **Paid social** — recommended platforms and budget allocation
- **Launch event** — a simple virtual event or webinar to build excitement

Organize as a week-by-week checklist leading up to {{launch_date}}.

```else```

### STEP 2c: Enterprise Launch Checklist

Comprehensive, multi-channel launch plan:

- **Demand generation** — paid campaigns across search, social, and display
- **Sales enablement** — battle cards, one-pagers, and demo scripts for the sales team
- **PR and analyst relations** — media outreach, analyst briefings, and embargo strategy
- **Event marketing** — launch event planning (virtual or in-person)
- **Partner marketing** — co-marketing with strategic partners
- **Content engine** — whitepapers, case studies, webinars, and video production
- **Customer marketing** — early adopter program and reference customer strategy
- **Internal readiness** — training support, sales, and customer success teams

Organize as a week-by-week checklist leading up to {{launch_date}}.

```endif```

## STEP 3: Draft Launch Day Timeline

Create an hour-by-hour timeline for the launch day of {{product_name}} on {{launch_date}}.

Include:
- **Pre-launch** (morning) — final checks, team alignment, last-minute prep
- **Launch moment** — what goes live and in what order
- **First 2 hours** — immediate actions after launch (social posts, emails, community engagement)
- **Midday** — check metrics, respond to feedback, handle any issues
- **End of day** — recap, celebrate, and identify what needs attention tomorrow

Assign responsibilities where possible based on a small team. If it is a solo launch, prioritize ruthlessly.

## STEP 4: Create Measurement Plan

Build a post-launch measurement plan for {{product_name}}.

Define:
1. **Key metrics** — the 3-5 numbers that tell you if the launch worked
2. **Tracking setup** — what to measure and how (keep it simple, no enterprise analytics stack needed)
3. **Day 1 report** — what to check and share with the team at end of launch day
4. **Week 1 review** — what to evaluate after the first full week
5. **30-day retrospective** — questions to answer one month after {{launch_date}}
6. **What good looks like** — realistic benchmarks for a {{budget_level}}-level launch

Keep it practical. Define metrics that are easy to track and directly tied to the launch goals from Step 1.

## ARTIFACTS

type: markdown
