# Workflow: Domain Finder

Find and verify domain availability for a product or brand concept.

## Purpose
Given a product idea or brand name, generate domain name candidates across multiple styles and check real-time availability — surfacing the best available options.

## Steps

### 1. Name Generation
Input: product description, brand tone (minimal / playful / technical / premium)
Output: 30+ candidate names across styles:
- Exact match (`productname.com`)
- Compound (`getproduct.com`, `useproduct.com`, `tryproduct.io`)
- Abstract / brandable (`kortex.ai`, `velvox.com`)
- Acronym / portmanteau
- TLD-as-word plays (`.io`, `.ai`, `.co`, `.dev`, `.so`)

### 2. Domain Availability Check
For each candidate:
- Check `.com`, `.io`, `.ai`, `.co`, `.dev`, `.app`
- Flag: ✅ Available | 🔴 Taken | ⚠️ Premium
- Tool: WHOIS API via Composio or `whois` CLI

### 3. Scoring & Ranking
Score each available domain on:
- Memorability (1–10)
- Brandability (1–10)
- SEO friendliness (1–10)
- Extension quality (.com > .io > .ai > others)

### 4. Output
- `domains.md` — ranked table of available domains with scores
- `domains.json` — raw data for downstream use
- Top 5 recommendations with rationale

## Config
```json
{
  "workflow": "domain-finder",
  "product_description": "...",
  "brand_tone": "technical | minimal | playful | premium",
  "max_candidates": 40,
  "tlds_to_check": [".com", ".io", ".ai", ".co", ".dev", ".app"]
}
```

## Integration
Can be triggered:
- As part of a `deep` IdeaForge session (auto-runs for top 3 ranked ideas)
- Standalone: `run_workflow.py --workflow=domain-finder --config=...`
- On-demand via SureThing chat

---
*IdeaForge Custom Workflow — Domain Finder*
