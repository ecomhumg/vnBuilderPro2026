# ArXiv Research

> **Skill ID**: SKILL-SDR-002
> **Tools**: arxivSearch, arxivFulltext

---

## Overview

Specialized skills for arXiv preprint discovery and fulltext retrieval.

---

## Tool Usage

### arxivSearch

- **Purpose**: Search arXiv preprint repository
- **Strengths**: CS, Physics, Math, Stats, Q-Bio
- **Parameters**: query, max_results

### arxivFulltext

- **Purpose**: Retrieve full PDF content
- **When**: extractUrl fails on arXiv links
- **Input**: arXiv ID (e.g., 2301.12345)

---

## Category Mapping

| Category | ArXiv Code |
|----------|------------|
| Computer Science | cs.* |
| Machine Learning | cs.LG, stat.ML |
| AI | cs.AI |
| Physics | physics.*, hep-*, cond-mat.* |
| Mathematics | math.* |
| Biology | q-bio.* |

---

## Best Practices

1. Include arXiv category in query for precision
2. Use arxivFulltext for guaranteed PDF access
3. Note: preprints may not be peer-reviewed

---

*Skill SKILL-SDR-002 | ArXiv Research*
