# W08-BiomedicalSearchWorker WORKFLOW

> **Worker ID**: W08
> **Tier**: 3 - Search Acquisition
> **Agents**: 24
> **Tools**: searchPubMed, pubmedFulltext, biorxivSearch, biorxivFulltext

---

## Overview

Searches biomedical literature across PubMed and bioRxiv.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive biomedical domain queries
- Get MeSH term suggestions

### Stage 2: Design

- Construct PubMed queries
- Prepare bioRxiv search

### Stage 3: Implement

- Execute searchPubMed for MEDLINE
- Execute biorxivSearch for preprints
- Use fulltext tools when needed

### Stage 4: Configure

- Apply MeSH filters
- Set recency preferences

### Stage 5: Test

- Validate PMIDs/DOIs
- Check fulltext availability

### Stage 6: Deploy

- Merge biomedical results
- Store: `results.pubmed[]`, `results.biorxiv[]`

---

## MeSH Usage

```
"Diabetes Mellitus"[MeSH] AND "Treatment"[MeSH]
```

---

*W08-BiomedicalSearchWorker | Tier 3 | ScholarDeepResearch-Workforce*
