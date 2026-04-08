---
name: deep-research
description: Multi-source research synthesis that searches the web, reads documents, and produces structured reports with citations. Use when the user asks to research a topic, compare options, investigate something in depth, or produce a report.
---

# Deep Research

Conduct thorough multi-source research and produce a structured, cited report. This is not a quick web search — it's a systematic investigation across multiple sources with synthesis and analysis.

## When to Use This Skill

- User asks to "research X", "investigate X", "deep dive into X"
- User wants a comparison of multiple options with evidence
- User needs a report, analysis, or briefing on a topic
- User says "find everything about X" or "I need to understand X thoroughly"
- User wants to make an informed decision and needs data

## Research Process

### Phase 1: Scope (30 seconds)

Before searching, define:
1. **Core question**: What exactly does the user want to know?
2. **Depth**: Quick overview (3-5 sources) or deep investigation (10-15 sources)?
3. **Output format**: Report, comparison table, executive summary, or raw findings?
4. **Constraints**: Time period? Geography? Industry? Budget range?

If the request is ambiguous, ask ONE clarifying question before proceeding.

### Phase 2: Search (2-5 minutes)

Execute searches in waves:

**Wave 1 — Broad discovery (3-4 searches):**
- Core topic search
- "[topic] 2025 2026" (recent coverage)
- "[topic] comparison" or "[topic] alternatives"
- "[topic] problems" or "[topic] criticism" (balance the view)

**Wave 2 — Deep dives (3-5 searches):**
- Follow the most promising leads from Wave 1
- Search for primary sources (company blogs, research papers, official docs)
- Search for expert opinions and practitioner experiences
- Check Reddit, HN, or forums for real-world feedback

**Wave 3 — Verification (1-2 searches):**
- Cross-check surprising claims
- Find counter-arguments to the dominant narrative
- Verify pricing, dates, and statistics from primary sources

### Phase 3: Synthesise (1-2 minutes)

Do NOT just list what each source says. Synthesise:

1. **Extract key findings** across all sources
2. **Identify consensus** — what do most sources agree on?
3. **Flag contradictions** — where do sources disagree? Who's more credible?
4. **Draw conclusions** — based on the evidence, what's the answer?
5. **Note gaps** — what couldn't you find? What needs more investigation?

### Phase 4: Output

Structure the report:

```markdown
# [Topic] — Research Report
*[Date] · [X] sources analysed*

## Executive Summary
[3-4 sentences: the answer, the key finding, and the confidence level]

## Key Findings

### Finding 1: [Title]
[2-3 paragraphs with evidence and citations]

### Finding 2: [Title]
[2-3 paragraphs with evidence and citations]

### Finding 3: [Title]
[2-3 paragraphs with evidence and citations]

## Comparison Table (if applicable)
| Factor | Option A | Option B | Option C |
|--------|----------|----------|----------|
| ...    | ...      | ...      | ...      |

## Risks & Considerations
- [What could go wrong or what to watch out for]

## Recommendation
[Clear, actionable recommendation based on the evidence]

## Sources
1. [Source name] — [URL] — [Key point used]
2. ...
```

## Quality Standards

- **Minimum 5 sources** for any research report
- **Maximum 15 sources** — beyond that, synthesise, don't add more
- **Prefer primary sources** over aggregators (company blog > TechCrunch summary)
- **Date-check everything** — flag if a source is >12 months old on a fast-moving topic
- **Never present one source's opinion as fact** — always attribute or cross-verify
- **Include at least one dissenting view** — balanced research is credible research

## Adapting to Context

| User type | Adapt output |
|-----------|-------------|
| Developer | Include code examples, GitHub links, technical benchmarks |
| Founder | Focus on market size, competition, pricing, GTM strategy |
| Analyst | Include data tables, charts, statistical evidence |
| General | Plain language, executive summary first, details below |
| Trader | Focus on price data, volume, sentiment, catalysts |

## What This Skill Does NOT Do

- Does not provide financial advice (present data, let user decide)
- Does not fabricate sources or statistics
- Does not present speculation as fact
- Does not skip the verification phase for speed
