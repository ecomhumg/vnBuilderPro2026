# Sample Execution

> **ScholarDeepResearch-Workforce v1.0.0**

---

## Example Query

**User**: "What are the latest advances in transformer architectures for NLP?"

---

## Tier 1: Query & Intelligence

**W01 Output**:

```json
{
  "clarified_query": "transformer architectures NLP advances 2023-2024",
  "domain": "Computer Science",
  "intent": "literature_review"
}
```

**W02 Output**: Domain = CS/AI, Priority = ArXiv > Scholar

---

## Tier 2: Search Strategy

**W04 Output**:

```
Keywords: ["transformer architecture", "NLP", "attention mechanism", "LLM"]
Boolean: ("transformer" OR "attention") AND ("NLP" OR "language model")
```

**W05 Output**: ArXiv (40%), Scholar (30%), Other (30%)

---

## Tier 3: Search Acquisition

**W06**: advancedScholarSearch → 20 papers
**W07**: arxivSearch → 15 preprints
**Merged**: 32 unique papers (after dedup)

---

## Tier 5: Critical Reading

**W11 Summary Example**:
> "The paper introduces a novel sparse attention mechanism reducing complexity from O(n²) to O(n log n). Key innovations include local-global attention patterns and dynamic sparsity selection..."

**W11 Questions**:

1. How does dynamic sparsity compare to fixed patterns?
2. What are the memory-accuracy tradeoffs?
3. Does this scale to 100B+ parameter models?

---

## Tier 7: Quality Validation

**W18 Citation Check**: 32/32 DOIs valid ✓
**W19 E-O Score**: 0.91 ✓

---

## Tier 8: Report Delivery

Final report with 32 sources, 10 visualizations, and structured synthesis.

---

*Sample Execution | ScholarDeepResearch-Workforce v1.0.0*
