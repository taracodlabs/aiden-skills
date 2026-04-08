---
name: competitor-analysis
description: Research competitors systematically — pricing, features, positioning, strengths, weaknesses — and produce a structured comparison document. Use when the user asks to analyse competitors, compare products, or understand their competitive landscape.
---

# Competitor Analysis

Systematically research and compare competitors, producing an actionable comparison document.

## When to Use This Skill

- User asks "analyse my competitors", "who competes with X"
- User wants a feature comparison or pricing comparison
- User asks "how does X compare to Y"
- User is evaluating tools, services, or products before a decision
- User wants to understand their competitive landscape for a pitch or strategy

## Process

### Step 1: Identify Competitors (2-3 minutes)

If the user names specific competitors, use those. If not:

1. Search "[product/category] alternatives"
2. Search "[product/category] vs"
3. Search "[product/category] competitors 2026"
4. Check G2, Capterra, or ProductHunt for the category
5. Identify 3-5 direct competitors and 2-3 indirect/adjacent ones

### Step 2: Research Each Competitor (3-5 minutes per competitor)

For each competitor, find:

**Company basics:**
- Name, URL, founding year, funding, team size
- One-line positioning statement (from their homepage)

**Product:**
- Core features (from their features page or docs)
- Pricing tiers (from pricing page — get exact numbers)
- Free tier details (what's included, what's limited)
- Target audience (who they market to)
- Platform support (web, desktop, mobile, OS)

**Positioning:**
- How they describe themselves (exact tagline)
- Key differentiators they claim
- Customer testimonials or case studies they highlight

**Weaknesses:**
- Common complaints (search "[product] problems" or "[product] review")
- Missing features users ask for (check their GitHub issues, community forums)
- Pricing objections

### Step 3: Synthesise into Comparison

**Comparison Table:**
```markdown
| Factor | Your Product | Competitor A | Competitor B | Competitor C |
|--------|-------------|-------------|-------------|-------------|
| Price | ₹499/mo | $20/mo | Free | $15/mo |
| Key feature 1 | ✅ | ✅ | ❌ | ✅ |
| Key feature 2 | ✅ | ❌ | ✅ | ❌ |
| Target user | Indie devs | Enterprises | Students | Teams |
| Platform | Windows | Web | Mac/Linux | Web |
| Free tier | 100 credits | 14-day trial | Full (limited) | Freemium |
```

**Positioning Map:**
Place competitors on two axes that matter to the user. Common axes:
- Price vs Features
- Simplicity vs Power
- Local vs Cloud
- Developer-focused vs General audience

**Strategic Insights:**
- Where is the gap in the market?
- What do all competitors do poorly?
- What's the user's unfair advantage?
- What would it take to win against each competitor?

### Step 4: Output Document

```markdown
# Competitive Analysis: [Category/Product]
*[Date] · [X] competitors analysed*

## Executive Summary
[3 sentences: who the main competitors are, where the gaps are, 
and what the strategic opportunity is]

## Competitor Profiles

### [Competitor A]
- **What they do**: [One line]
- **Pricing**: [Tiers with exact numbers]
- **Strengths**: [2-3 bullets]
- **Weaknesses**: [2-3 bullets]
- **Why users choose them**: [Key draw]
- **Why users leave**: [Key complaint]

[Repeat for each competitor]

## Comparison Table
[Full feature/pricing comparison]

## Key Insights
1. [Insight about market gap]
2. [Insight about pricing opportunity]
3. [Insight about underserved segment]

## Recommended Strategy
[2-3 paragraphs on how to position and win]

## Sources
[Numbered list with URLs]
```

## Quality Standards

- Always get exact pricing — don't say "affordable", say "₹499/month"
- Verify claims from at least 2 sources
- Include at least one user review/complaint per competitor
- Present strengths AND weaknesses for every competitor — balanced analysis
- Date-stamp the analysis — competitive landscapes change fast
