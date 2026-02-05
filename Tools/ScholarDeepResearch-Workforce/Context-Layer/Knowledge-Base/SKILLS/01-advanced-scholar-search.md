# Advanced Scholar Search

> **Skill ID**: SKILL-SDR-001
> **Tools**: advancedScholarSearch, scholarSearch

---

## Overview

Mastery of Google Scholar search with reranking for optimal academic paper discovery.

---

## Tool Usage

### advancedScholarSearch

- **Purpose**: Broad scholarly search with AI reranking
- **When**: Default for general queries
- **Parameters**: query, count (default: 20)

### scholarSearch

- **Purpose**: Citation-based and strict title searches
- **When**: Known title or citation lookup
- **Parameters**: query, exact_title (optional)

---

## Query Optimization

| Technique | Example |
|-----------|---------|
| Phrase Match | "machine learning" |
| Author Filter | author:Smith |
| Year Range | 2020..2024 |
| Site Filter | site:arxiv.org |
| Exclusion | -review |

---

## Best Practices

1. Use `count: 20` unless user specifies
2. Prefer advancedScholarSearch for broad queries
3. Use scholarSearch for specific titles
4. Combine with domain-specific databases for completeness

---

*Skill SKILL-SDR-001 | Advanced Scholar Search*
