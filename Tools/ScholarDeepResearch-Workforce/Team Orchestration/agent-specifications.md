# Agent Specifications

> **ScholarDeepResearch-Workforce v1.0.0**
> 528 Agents (24 per worker × 22 workers)

---

## Agent Architecture (ROMA-24)

Each worker contains 24 agents distributed across the ROMA 6-stage pipeline:

| Stage | Agents | Role |
|-------|--------|------|
| Intake | 4 | Input processing |
| Design | 4 | Strategy planning |
| Implement | 6 | Core execution |
| Configure | 4 | Parameterization |
| Test | 4 | Validation |
| Deploy | 2 | Output delivery |

---

## Cognitive Patterns (L6)

All agents implement L6 cognitive chains:

1. **Perception**: Input understanding and context extraction
2. **Reasoning**: Domain-specific problem solving
3. **Planning**: Action sequencing and optimization
4. **Execution**: Tool invocation and task completion
5. **Reflection**: Output quality assessment
6. **Learning**: Pattern recognition and improvement

---

## Tool Assignments

| Worker | Primary Tools |
|--------|---------------|
| W06 | advancedScholarSearch, scholarSearch |
| W07 | arxivSearch, arxivFulltext |
| W08 | searchPubMed, pubmedFulltext, biorxivSearch, biorxivFulltext |
| W21 | patentSearch, WebSearchReranked |
| W09, W10 | extractUrl |
| W15, W16 | code_interpreter |
| W14, W16, W20 | image generation |

---

*Agent Specifications | ScholarDeepResearch-Workforce v1.0.0*
