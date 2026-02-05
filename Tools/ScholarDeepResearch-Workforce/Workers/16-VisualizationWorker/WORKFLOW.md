# W16-VisualizationWorker WORKFLOW

> **Worker ID**: W16
> **Tier**: 6 - Analysis & Synthesis
> **Agents**: 24
> **Tools**: code_interpreter, image generation

---

## Overview

Creates data visualizations and visual reports.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive analysis results
- Identify visualization needs

### Stage 2: Design

- Select chart types
- Plan visual layout

### Stage 3: Implement

- Generate matplotlib/seaborn charts
- Create custom images
- Apply styling

### Stage 4: Configure

- Set ≥300 DPI resolution
- Configure color schemes

### Stage 5: Test

- Validate chart accuracy
- Check accessibility

### Stage 6: Deploy

- Include in reports
- Store: `visuals.charts[]`

---

## Chart Library

| Type | Library |
|------|---------|
| Line/Bar | matplotlib |
| Heatmap | seaborn |
| Network | networkx |
| Custom | image generation |

---

*W16-VisualizationWorker | Tier 6 | ScholarDeepResearch-Workforce*
