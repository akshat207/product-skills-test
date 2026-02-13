---
name: market-research
description: Conduct structured market research and competitive analysis for product decisions. Use when the user asks to research a market, analyze competitors, validate a product idea, size a market (TAM/SAM/SOM), understand customer segments, evaluate pricing strategies, or assess market entry opportunities. Produces actionable research briefs with data-backed insights, not generic overviews. Especially useful for bootstrapped founders and product managers evaluating new opportunities, pivots, or expansions.
---

# Market Research Agent

## Overview

This skill conducts structured, web-powered market research to produce actionable intelligence for product and business decisions. It goes beyond surface-level summaries by triangulating multiple sources, quantifying market dynamics, and surfacing non-obvious insights.

The skill is designed for product leaders and founders who need to make decisions fast — not academic researchers who need exhaustive literature reviews.

## Core Principles

1. **Data over opinions**: Every claim should be backed by a source, a number, or a clear reasoning chain. Flag when something is an estimate vs. a verified figure.
2. **So-what framing**: Every finding should connect to a decision or action. Don't just report that "the market is growing" — say what that means for the user's specific situation.
3. **Honest uncertainty**: Clearly distinguish between verified facts, reasonable estimates, and speculation. Use confidence levels (High / Medium / Low) for key claims.
4. **Bootstrapper-friendly**: Default to scrappy, actionable insights rather than consulting-firm-style frameworks that require massive budgets to act on.
5. **Recency matters**: Always prefer recent data. Flag when data is older than 12 months. Use web search aggressively to find the latest numbers.

## Research Modes

The skill supports several research modes depending on what the user needs. Identify which mode(s) apply based on the user's request, then follow the corresponding workflow.

### Mode 1: Market Sizing (TAM / SAM / SOM)

**When to use**: User wants to understand how big an opportunity is. Phrases like "how big is the market for X", "what's the TAM", "is this market worth entering".

**Workflow**:
1. **Define the market boundaries** — What exactly are we measuring? Clarify geography, customer segment, product category.
2. **Top-down sizing** — Search for industry reports, analyst estimates, and public company data to establish TAM.
3. **Bottom-up validation** — Estimate from unit economics: (number of potential customers) × (average revenue per customer) × (purchase frequency).
4. **SAM narrowing** — Apply realistic filters: geography, segment, channel, price point.
5. **SOM estimation** — Based on competitive dynamics, distribution advantages, and realistic capture rate for a bootstrapped/early-stage company.
6. **Growth trajectory** — CAGR, key growth drivers, potential headwinds.

**Output format**:
```
## Market Sizing: [Market Name]

### Definitions
- **Market**: [precise definition of what's being measured]
- **Geography**: [target geography]
- **Time horizon**: [year of estimates]

### TAM (Total Addressable Market)
- **Estimate**: [₹/$ figure]
- **Source(s)**: [citations]
- **Methodology**: [top-down / bottom-up / both]
- **Confidence**: [High / Medium / Low]

### SAM (Serviceable Addressable Market)
- **Estimate**: [₹/$ figure]
- **Key filters applied**: [list]
- **Confidence**: [High / Medium / Low]

### SOM (Serviceable Obtainable Market)
- **Year 1 estimate**: [₹/$ figure]
- **Year 3 estimate**: [₹/$ figure]
- **Assumptions**: [list key assumptions]
- **Confidence**: [Low — this is always speculative]

### Growth Dynamics
- **CAGR**: [%]
- **Key drivers**: [list]
- **Headwinds**: [list]

### So What
[2-3 sentences on what this means for the user's decision]
```

---

### Mode 2: Competitive Landscape

**When to use**: User wants to understand who they're competing with. Phrases like "who are the competitors", "competitive analysis", "how does X compare to Y".

**Workflow**:
1. **Identify the competitive set** — Direct competitors, indirect competitors, and substitutes. Search broadly first, then narrow.
2. **Profile each competitor** — Funding, revenue (if available), team size, pricing, positioning, key features, target customer.
3. **Map the landscape** — Find meaningful axes to differentiate (e.g., price vs. depth, self-serve vs. enterprise, generalist vs. specialist).
4. **Identify gaps and patterns** — Where is the market underserved? What are competitors ignoring? Where is there convergence?
5. **Assess competitive moats** — Network effects, data advantages, brand, switching costs, distribution.

**Output format**:
```
## Competitive Landscape: [Market/Category]

### Competitive Set
| Company | Type | Founded | Funding/Revenue | Pricing | Target Segment | Key Differentiator |
|---------|------|---------|-----------------|---------|----------------|-------------------|
| ...     | Direct / Indirect / Substitute | ... | ... | ... | ... | ... |

### Positioning Map
[Describe the 2 most meaningful axes and where each player sits]

### Patterns & Gaps
- **Convergence**: [What everyone is doing]
- **Underserved segments**: [Who's being ignored]
- **Emerging trends**: [What's changing]

### Competitive Moats Assessment
| Company | Moat Type | Strength |
|---------|-----------|----------|
| ...     | ...       | Strong / Medium / Weak |

### So What
[What this means for the user's positioning and strategy]
```

---

### Mode 3: Customer & Segment Analysis

**When to use**: User wants to understand who buys and why. Phrases like "who's the target customer", "customer segments", "buyer persona", "willingness to pay".

**Workflow**:
1. **Identify segments** — Search for how the market naturally segments (by company size, role, use case, geography, behavior).
2. **Profile each segment** — Size, pain points, current solutions, budget, decision-making process, channels to reach them.
3. **Assess attractiveness** — Score each segment on: size, growth, accessibility, willingness to pay, competition intensity, strategic fit.
4. **Prioritize** — Recommend which segments to target first and why, using a beachhead market framework.

**Output format**:
```
## Customer Segments: [Market]

### Segment Overview
| Segment | Size | Key Pain Point | Current Solution | WTP | Accessibility | Priority |
|---------|------|----------------|------------------|-----|---------------|----------|
| ...     | ...  | ...            | ...              | ... | ...           | High/Med/Low |

### Priority Segment Deep Dive: [Top Segment]
- **Profile**: [demographics, firmographics]
- **Jobs to be done**: [list]
- **Pain points**: [ranked by severity]
- **Current alternatives**: [what they use today and why it's insufficient]
- **Decision-making**: [who decides, what influences them, buying cycle]
- **Channels**: [how to reach them cost-effectively]

### So What
[Recommended beachhead strategy]
```

---

### Mode 4: Pricing Research

**When to use**: User wants to understand how to price. Phrases like "how should I price", "pricing strategy", "what are others charging", "willingness to pay".

**Workflow**:
1. **Map competitor pricing** — Collect all visible pricing from competitors (tiers, models, discounts).
2. **Identify pricing models** — Freemium, subscription, one-time, usage-based, cohort-based, tiered.
3. **Analyze value metrics** — What unit does the customer care about? Per user, per project, per outcome?
4. **Assess price sensitivity** — Based on segment, alternatives, and switching costs.
5. **Recommend pricing architecture** — Model, tiers, anchor pricing, and positioning.

---

### Mode 5: Opportunity Assessment

**When to use**: User is evaluating whether to enter a market or launch a product. This is the most comprehensive mode — it combines elements of all other modes into a go/no-go brief.

**Workflow**:
1. Run a condensed version of Market Sizing (Mode 1)
2. Run a condensed version of Competitive Landscape (Mode 2)
3. Assess timing — Why now? What's changed?
4. Evaluate fit — Does this align with the user's strengths, assets, and distribution?
5. Identify key risks and unknowns
6. Provide a clear recommendation with confidence level

**Output format**:
```
## Opportunity Assessment: [Opportunity Name]

### Executive Summary
[3-4 sentence verdict]

### Market Opportunity
- **Size (SAM)**: [figure]
- **Growth**: [CAGR]
- **Timing signal**: [why now]

### Competitive Dynamics
- **Number of direct competitors**: [count]
- **Market concentration**: [fragmented / consolidating / dominated]
- **Key differentiator available**: [yes/no + what]

### Fit Assessment
- **Strengths alignment**: [how user's existing assets help]
- **Distribution advantage**: [existing channels, audience, brand]
- **Capability gaps**: [what's missing]

### Key Risks
| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| ...  | High/Med/Low | High/Med/Low | ... |

### Recommendation
**[GO / CONDITIONAL GO / NO-GO]** — [Confidence: High/Medium/Low]
[Rationale in 2-3 sentences]

### If GO: Suggested Next Steps
1. [First validation step]
2. [Second step]
3. [Third step]
```

---

## Research Execution Guidelines

### Web Search Strategy
- **Start broad, then narrow**: Begin with category-level searches, then drill into specifics.
- **Triangulate**: Never rely on a single source for market size or growth figures. Cross-reference at least 2-3 sources.
- **Prioritize primary sources**: Company blogs, SEC filings, press releases, and official reports over aggregator sites.
- **Search for contrarian views**: After finding the consensus, actively search for "why [market] is overhyped" or "[competitor] problems" to get the full picture.
- **Check recency**: Always note the date of data. Markets can shift dramatically in 12 months.
- **Use Indian context where relevant**: If the user's market is India, search for India-specific data, pricing, and competitive dynamics rather than defaulting to US/global data.

### Quality Checks
Before delivering any research output, verify:
- [ ] All market size figures have sources cited
- [ ] Competitor data is current (within 12 months)
- [ ] Confidence levels are assigned to key claims
- [ ] "So What" section connects findings to user decisions
- [ ] Honest about gaps: clearly state what you couldn't find or verify
- [ ] Numbers pass the smell test (e.g., a niche B2B market probably isn't $100B)

### Handling Uncertainty
- If reliable data doesn't exist, say so explicitly rather than guessing.
- For estimates, show your math so the user can adjust assumptions.
- Use ranges rather than point estimates when data is sparse: "₹500Cr - ₹800Cr based on [methodology]"
- Flag emerging markets where historical data may not predict the future.

## Adapting to Context

### For Bootstrapped Founders
- Emphasize unit economics and capital efficiency over total market size
- Focus on segments reachable without massive marketing budgets
- Highlight organic distribution channels and community-driven growth
- Consider the "1,000 true fans" angle for niche markets

### For Product Managers at Companies
- Frame findings in terms of product strategy and roadmap implications
- Connect market dynamics to feature prioritization
- Include build-vs-buy-vs-partner analysis where relevant
- Map competitive features to user needs

### For Investors/Fundraising Context
- Lead with TAM/SAM/SOM with clear methodology
- Emphasize growth vectors and timing
- Include comparable company analysis
- Frame competitive landscape as "why this team can win"

## Output Delivery

### Default: Markdown Document
For most research requests, produce a structured markdown document following the relevant mode's output format. This should be saved as a `.md` file the user can reference later.

### For Quick Questions
If the user asks a narrow, specific question (e.g., "what's the CAGR for edtech in India?"), answer directly with sources — don't produce a full report.

### For Complex Research
If the research requires more than one mode, produce a single comprehensive document that flows logically rather than separate reports. Use the Opportunity Assessment (Mode 5) format as the wrapper.

## References

See `references/research-prompts.md` for a library of effective search query patterns for different research scenarios.

See `references/data-sources.md` for a curated list of reliable data sources by industry and geography.
