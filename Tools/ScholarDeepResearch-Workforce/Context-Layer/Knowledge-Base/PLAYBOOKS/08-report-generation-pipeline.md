# Report Generation Pipeline

> **Playbook ID**: PLAYBOOK-SDR-008
> **Domain**: ScholarDeepResearch-Workforce
> **Version**: 1.0.0

---

## Overview

Generates customized research reports combining analytical insights with visualizations.

---

## Report Types

| Type | Structure | Use Case |
|------|-----------|----------|
| Executive Summary | Brief, key findings | Quick overview |
| Literature Review | Comprehensive, thematic | Academic papers |
| Technical Analysis | Detailed, data-heavy | Research projects |
| Visual Report | Chart-focused, minimal text | Presentations |
| Comparative Analysis | Side-by-side evaluation | Decision support |

---

## Generation Pipeline

```mermaid
flowchart LR
    I[Research Insights] --> S[Structure Selection]
    S --> C[Content Assembly]
    C --> V[Visualization Integration]
    V --> F[Formatting]
    F --> Q[Quality Check]
    Q --> OUT[Final Report]
```

---

## Content Assembly Rules

1. **Overview First**: Lead with collective insight summary
2. **Expansive Responses**: 50+ words per article summary
3. **Citation Integration**: Inline references with full bibliography
4. **Visual Balance**: At least 1 visualization per major section

---

## Quality Standards

| Metric | Threshold |
|--------|-----------|
| Citation Accuracy | 100% |
| Source Diversity | ≥8 academic works |
| Visual Quality | ≥300 DPI |
| Readability | Flesch score ≥60 |

---

*Playbook PLAYBOOK-SDR-008 | Report Generation Pipeline*
