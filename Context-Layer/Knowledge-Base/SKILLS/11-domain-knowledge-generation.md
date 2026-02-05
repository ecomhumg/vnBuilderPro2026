---
always: false
tier: [1,2]
description: "Templates for generating domain-specific PLAYBOOKS and SKILLS"
core_modules: [SkillsLoader]
---

# SKILL: Domain Knowledge Generation

> **Purpose**: Templates for generating domain-specific PLAYBOOKS and SKILLS during workforce creation.

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Output** | Domain-specific Knowledge-Base |
| **PLAYBOOKS** | 8-12 per domain |
| **SKILLS** | 10-14 per domain |

---

## PLAYBOOK Generation Template

### Template Structure

```markdown
# PLAYBOOK: {Domain} {Process Name}

> **Purpose**: {One-line description of the playbook's goal}

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Domain** | {Domain Name} |
| **Process** | {Process Name} |
| **Workers** | {Relevant worker IDs} |

---

## Process Flow

{Mermaid diagram showing the process}

---

## Steps

### Step 1: {Step Name}

{Detailed instructions}

### Step 2: {Step Name}

{Detailed instructions}

---

## Quality Criteria

- [ ] {Criterion 1}
- [ ] {Criterion 2}

---

*PLAYBOOK v2.0.0 | {DomainName}-Workforce*
```

---

## Standard PLAYBOOKS per Domain

### Research Domain (Example)

1. Multi-Database Search Orchestration
2. Critical Reading Pipeline
3. Citation Validation Protocol
4. Multimodal Document Analysis
5. Data Analysis Visualization
6. Fulltext Retrieval Orchestration
7. Query Clarification Protocol
8. Report Generation Pipeline
9. Academic Integrity Enforcement
10. Efficiency Optimization

### Operations Domain

1. Workflow Orchestration
2. Data Ingestion Pipeline
3. Transformation Processing
4. Quality Validation Protocol
5. Error Handling Patterns
6. Monitoring Dashboard
7. Alert Management
8. Efficiency Optimization

---

## SKILL Generation Template

### Template Structure

```markdown
# SKILL: {Skill Name}

> **Purpose**: {One-line description}

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Input** | {Input type} |
| **Output** | {Output type} |
| **Tools** | {Required tools} |

---

## Implementation

### Step 1: {Step}

{Instructions}

---

## Examples

| Input | Output |
|-------|--------|
| {Example 1} | {Result 1} |

---

*SKILL v2.0.0 | {DomainName}-Workforce*
```

---

## Standard SKILLS per Domain

### Research Domain (Example)

1. Advanced Scholar Search
2. ArXiv Research
3. Biomedical Research
4. Patent Web Search
5. Content Extraction
6. Summarization Questioning
7. Critical Inquiry Analysis
8. Contrast Perspective Analysis
9. Structure Diagramming
10. Statistical Analysis
11. Visualization Generation
12. Citation Verification

---

## Auto-Generation Rules

| Domain Type | PLAYBOOKS | SKILLS |
|-------------|-----------|--------|
| Research | 10 | 12 |
| Operations | 8 | 10 |
| Analytics | 8 | 12 |
| Creative | 6 | 8 |

---

*SKILL v2.0.0 | Domain Knowledge Generation | MASDesign-Workforce*
