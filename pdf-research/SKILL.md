---
name: pdf-research
description: Read multiple PDF documents, extract key findings, and synthesise into a structured report with citations. Use when the user uploads PDFs and asks to analyse, summarise, compare, or extract information from them.
---

# PDF Research

Read, analyse, and synthesise information across multiple PDF documents into a structured report.

## When to Use This Skill

- User uploads one or more PDFs and asks to "summarise", "analyse", or "compare"
- User says "read these documents and tell me X"
- User wants to extract specific information from PDFs (pricing, terms, data)
- User asks for a synthesis across multiple research papers or reports
- User says "what do these documents say about X"

## Process

### Step 1: Ingest

For each PDF:
1. Extract full text (use PDF reader tool or `pdftotext`)
2. Note: total pages, title, author (if available), date
3. Create a one-line summary of what the document is about

```
Document inventory:
1. "Q3-Financial-Report.pdf" — 24 pages — Company quarterly financials
2. "Market-Analysis-2026.pdf" — 48 pages — Industry market overview
3. "Competitor-Deck.pdf" — 15 pages — Competitor product presentation
```

### Step 2: Extract

Based on what the user wants, extract relevant information:

**For summaries:** Key points, conclusions, recommendations from each document
**For comparisons:** Common dimensions across all documents (pricing, features, methodology)
**For specific questions:** Targeted extraction of the exact data points requested
**For research synthesis:** Findings, methodology, data, conclusions per document

Tag every extraction with its source:
```
[Doc 1, p.12] Revenue grew 23% YoY to ₹4.2 Cr
[Doc 2, p.7] Market expected to reach $45B by 2028
[Doc 3, p.3] Competitor launched feature X in Q2
```

### Step 3: Synthesise

Cross-reference findings across documents:
- Where do documents agree? (consensus)
- Where do they contradict? (flag for user)
- What patterns emerge across all documents?
- What's missing that none of the documents address?

### Step 4: Output

```markdown
# Research Synthesis: [Topic]
*[Date] · [X] documents analysed · [Y] total pages*

## Documents Reviewed
1. [Title] — [Pages] — [One-line description]
2. ...

## Executive Summary
[3-5 sentences summarising the combined findings]

## Key Findings

### Finding 1: [Title]
[Synthesis across documents]
Sources: [Doc 1, p.X], [Doc 3, p.Y]

### Finding 2: [Title]
[Synthesis across documents]
Sources: [Doc 2, p.X]

## Comparison Table (if comparing documents)
| Dimension | Doc 1 | Doc 2 | Doc 3 |
|-----------|-------|-------|-------|
| ...       | ...   | ...   | ...   |

## Contradictions & Gaps
- [Doc 1] says X, but [Doc 2] says Y — needs verification
- None of the documents address [gap topic]

## Recommendations
[Based on the combined evidence, what should the user do?]
```

## Quality Standards

- Every claim must cite the source document and page number
- Never fabricate information that isn't in the documents
- If a document is unclear, say so — don't guess
- For large documents (50+ pages): focus on executive summary, conclusions, and key data tables first
- Present the synthesis, not just summaries — the value is in connecting information across documents
