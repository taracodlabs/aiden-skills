---
name: content-planner
description: Generate a content calendar with post ideas, hooks, formats, and scheduling for social media, newsletters, or blogs. Use when the user asks to plan content, create a content calendar, or generate post ideas.
---

# Content Planner

Generate a structured content calendar with ideas, hooks, formats, and optimal posting schedule.

## When to Use This Skill

- User asks "plan my content for the month" or "give me post ideas"
- User wants a content calendar for X, LinkedIn, Instagram, newsletter, or blog
- User says "what should I post about" or "I need content ideas"
- User wants to build an audience or grow engagement on a platform

## Process

### Step 1: Understand the Context

Identify (ask if not clear):
1. **Platform**: X/Twitter, LinkedIn, Instagram, newsletter, blog, YouTube
2. **Niche/topic**: What do they talk about? (AI, trading, startups, design, etc.)
3. **Audience**: Who are they trying to reach?
4. **Frequency**: How often do they want to post? (daily, 3x/week, weekly)
5. **Voice**: Professional, casual, technical, provocative, educational?
6. **Goal**: Followers? Leads? Sales? Authority?

### Step 2: Generate Content Pillars

Every account needs 3-5 content pillars — recurring themes that define what you're known for.

Example for a solo dev founder:
1. **Build in public** — share what you're building, progress, metrics
2. **Technical insights** — how things work under the hood, architecture decisions
3. **Industry takes** — opinions on trends, tools, news
4. **Lessons learned** — failures, pivots, things that surprised you
5. **Results/proof** — screenshots, numbers, user feedback

### Step 3: Generate the Calendar

For each posting slot, generate:

```markdown
## Week 1

### Monday — [Pillar: Build in Public]
**Format**: Thread (5-7 tweets)
**Hook**: "I spent 12 months building an AI that runs locally. Here's what broke (and what didn't):"
**Key points**: Architecture decisions, biggest failure, one surprise win
**CTA**: "Download free: [link]"
**Best time**: 9:00 AM IST / 8:30 PM PST

### Wednesday — [Pillar: Technical Insight]
**Format**: Single post + image
**Hook**: "Most AI agents retry on failure. Here's why that's wrong →"
**Key points**: Explain replanning vs retrying, show code snippet
**CTA**: "Agree? What's your failure recovery strategy?"
**Best time**: 12:00 PM IST / 9:00 AM PST

### Friday — [Pillar: Industry Take]
**Format**: Short post (under 280 chars)
**Hook**: "ChatGPT costs ₹1,650/month and can't touch your files. That's not an AI assistant. That's a chatbot with a premium label."
**CTA**: None (let engagement drive reach)
**Best time**: 6:00 PM IST / 5:00 PM PST
```

### Step 4: Output the Full Calendar

```markdown
# Content Calendar — [Month Year]
*Platform: [X/LinkedIn/etc] · Frequency: [X posts/week]*
*Pillars: [Pillar 1] · [Pillar 2] · [Pillar 3]*

## Week 1
[Posts with hooks, formats, timing]

## Week 2
[Posts with hooks, formats, timing]

## Week 3
[Posts with hooks, formats, timing]

## Week 4
[Posts with hooks, formats, timing]

---

## Content Bank (Evergreen Ideas)
[10 additional post ideas that can be used anytime]

## Repurpose Plan
- Thread → LinkedIn article
- Best-performing post → Newsletter lead
- Technical post → Blog tutorial
- Hot take → Quote graphic for Instagram
```

## Platform-Specific Guidelines

**X/Twitter:**
- Hooks must be <100 chars for maximum engagement
- Threads: 5-7 tweets, each standalone valuable
- Best times: 9 AM, 12 PM, 6 PM in target timezone
- Use line breaks for readability, no walls of text

**LinkedIn:**
- First line is everything — must stop the scroll
- 1,200-1,500 chars is the sweet spot
- Personal stories outperform pure advice
- Best times: 8 AM, 12 PM on weekdays
- End with a question to drive comments

**Newsletter:**
- Subject line <50 chars, create curiosity
- One core topic per issue, go deep
- Include one actionable takeaway
- CTA at the end, not the middle

## Quality Standards

- Every post must have a hook that stops scrolling
- No generic advice — be specific, use numbers, show examples
- Every CTA should be clear and single-action
- Balance value posts (80%) with promotional posts (20%)
- Include 2-3 "engagement bait" posts per month (questions, polls, hot takes)
