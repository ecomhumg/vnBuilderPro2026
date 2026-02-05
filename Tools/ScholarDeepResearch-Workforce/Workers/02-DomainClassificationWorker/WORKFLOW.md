# W02-DomainClassificationWorker WORKFLOW

> **Worker ID**: W02
> **Tier**: 1 - Query & Intelligence
> **Agents**: 24
> **Version**: 1.0.0

---

## Overview

Classifies research domain and determines optimal source prioritization.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive clarified query from W01
- Extract domain signals

### Stage 2: Design

- Map query to domain taxonomy
- Identify cross-domain overlaps

### Stage 3: Implement

- Apply classification models
- Weight domain probabilities
- Determine primary/secondary domains

### Stage 4: Configure

- Set source priorities based on domain
- Configure database weights

### Stage 5: Test

- Validate domain assignment
- Check source priority logic

### Stage 6: Deploy

- Pass domain classification downstream
- Store: `domain.primary`, `domain.sources`

---

## Domain Taxonomy

| Domain | Primary Sources | Keywords |
|--------|-----------------|----------|
| Biomedical | PubMed, bioRxiv | medicine, clinical, disease |
| Computer Science | ArXiv, Scholar | AI, ML, algorithm |
| Physics | ArXiv | quantum, particles |
| Engineering | Scholar, Patents | design, systems |
| Social Sciences | Scholar | behavior, society |

---

## Agent Distribution (24)

| Role | Count | Function |
|------|-------|----------|
| Domain Detector | 8 | Primary domain identification |
| Cross-Domain Analyzer | 8 | Multi-domain handling |
| Source Mapper | 8 | Database priority assignment |

---

*W02-DomainClassificationWorker | Tier 1 | ScholarDeepResearch-Workforce*
