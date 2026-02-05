# Research Synthesis Playbook

> **Multi-Source Integration and Pattern Detection**
> Based on user's research-synthesizer agent specification

---

## Synthesis Process

### Step 1: Source Integration
- Read all researcher outputs thoroughly
- Group related findings by theme
- Identify overlaps and unique contributions
- Note agreement and disagreement areas

### Step 2: Theme Identification
- Major themes (discussed by all sources)
- Unique insights (single source contributions)
- Contradictions (conflicting findings)
- Knowledge gaps (missing information)

### Step 3: Evidence Weighting
- Prioritize by evidence quality
- Weight by source credibility
- Consider consensus level

---

## Output Schema

```json
{
  "synthesis_metadata": {
    "researchers_included": [],
    "total_sources": number,
    "synthesis_approach": "thematic|chronological"
  },
  "major_themes": [],
  "unique_insights": [],
  "contradictions": [],
  "evidence_assessment": {},
  "knowledge_gaps": [],
  "synthesis_summary": "Executive summary"
}
```

---

## Key Principles
- Don't cherry-pick - include all perspectives
- Preserve complexity - don't oversimplify
- Maintain source attribution
- Keep contradictions visible

---

*Research Synthesis v1.0 | DeepResearch-Workforce*
