# Query Clarification Protocol

> **Playbook ID**: PLAYBOOK-SDR-007
> **Domain**: ScholarDeepResearch-Workforce
> **Version**: 1.0.0

---

## Overview

Parses and disambiguates research queries for optimal search execution.

---

## Query Analysis Framework

| Dimension | Extraction |
|-----------|------------|
| Topic | Main subject area |
| Scope | Broad/Narrow/Specific |
| Timeframe | Date range requirements |
| Source Preference | Academic/Patents/Web |
| Output Type | Summary/Analysis/Data |

---

## Disambiguation Protocol

1. **Entity Resolution**: Identify ambiguous terms
2. **Context Inference**: Use conversation history
3. **Domain Detection**: Classify research field
4. **Intent Classification**: Understand user goal

---

## Domain Classification

| Domain | Keywords | Primary Sources |
|--------|----------|-----------------|
| Biomedical | medicine, clinical, disease | PubMed, bioRxiv |
| Computer Science | AI, ML, algorithm | ArXiv, Scholar |
| Physics | quantum, particles, physics | ArXiv |
| Chemistry | synthesis, molecular | Scholar, PubMed |
| Social Sciences | behavior, society, policy | Scholar |
| Engineering | design, systems, materials | Scholar, Patents |

---

## Output Format

```json
{
  "original_query": "...",
  "clarified_query": "...",
  "domain": "...",
  "scope": "...",
  "timeframe": {"start": null, "end": null},
  "source_priority": ["Scholar", "ArXiv"],
  "search_terms": ["term1", "term2"],
  "boolean_query": "(term1 OR term2) AND term3"
}
```

---

*Playbook PLAYBOOK-SDR-007 | Query Clarification Protocol*
