---
name: morning-briefing
description: Generate a personalised daily briefing covering weather, market snapshot, trending news, pending tasks, and calendar — delivered as a concise summary. Use when the user asks for a briefing, daily summary, or morning update.
---

# Morning Briefing

Generate a concise, actionable daily briefing tailored to the user's context.

## When to Use This Skill

- User says "give me my briefing", "morning update", "what's happening today"
- User asks "what do I need to know today" or "catch me up"
- Scheduled task triggers at user's preferred time (e.g., 8:00 AM daily)

## Briefing Structure

Generate each section in order. Skip any section where data is unavailable.

### 1. Weather (if location known)
```
☀️ Mumbai: 32°C, clear skies. High 35°C. No rain expected.
```
Source: web search "[city] weather today"

### 2. Market Snapshot (if user tracks markets)
```
📈 Markets:
  NIFTY 50: 22,450 (+0.8%) | Bank NIFTY: 48,120 (+0.5%)
  Sensex: 73,890 (+0.7%)
  Top gainer: TATAMOTORS +3.2% | Top loser: WIPRO -1.8%
  FII: +₹1,200Cr | DII: +₹800Cr
```
Source: web search "NIFTY today" or yfinance API

### 3. Trending News (3-5 items)
```
📰 Headlines:
  1. RBI holds repo rate at 6.5% — markets react positively
  2. OpenAI launches GPT-5 turbo — 2x faster, same price
  3. SEBI tightens F&O margin rules effective April 15
```
Source: web search "India news today" + "tech news today" + user-specific topics

### 4. Pending Tasks / Goals
```
📋 Your tasks:
  • [From GOALS.md or task system] Ship newsletter issue #6
  • [From GOALS.md] Fix Archon deployment bug
  • [From scheduled tasks] NSE scan runs at 9:15 AM
```
Source: local goals file, task queue, scheduled tasks

### 5. Calendar (if connected)
```
📅 Today:
  10:00 AM — Standup with team
  2:00 PM — Client call (Alex, re: Q2 roadmap)
  4:30 PM — Dentist
```
Source: calendar integration or user-provided schedule

### 6. One Actionable Insight
```
💡 Based on your recent work: You've been researching AI agents for 5 sessions.
   Consider writing that Ship It article while context is fresh.
```
Source: conversation history, memory, patterns

## Output Format

Deliver as a single, clean message — not multiple tool calls. The briefing should be scannable in under 60 seconds.

```
Good morning! Here's your briefing for [Day, Date]:

[Weather line]

[Market snapshot — 3-4 lines max]

[Headlines — 3-5 bullet points]

[Tasks — from goals/queue]

[Calendar — today's events]

[One insight or suggestion]

That's it. Have a productive day.
```

## Customisation

Adapt based on what you know about the user:
- **Trader**: Lead with markets, include FII/DII data, mention key levels
- **Developer**: Lead with tech news, include GitHub trending, mention build status
- **Founder**: Lead with industry news, mention KPIs, include competitor moves
- **General**: Balanced mix, keep each section to 2-3 lines

## Scheduling

This skill works best as a scheduled daily task:
- Default time: 8:00 AM in user's timezone
- Delivery: dashboard notification, Telegram message, or voice readout
- Frequency: daily on weekdays, skip weekends (configurable)
