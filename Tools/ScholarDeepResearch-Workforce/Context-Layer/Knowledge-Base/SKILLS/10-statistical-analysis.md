# Statistical Analysis

> **Skill ID**: SKILL-SDR-010
> **Tools**: code_interpreter

---

## Overview

Skills for statistical analysis using Python in code_interpreter.

---

## Capabilities

| Category | Methods |
|----------|---------|
| Descriptive | Mean, median, std, quartiles |
| Inferential | t-test, ANOVA, chi-square |
| Correlation | Pearson, Spearman, regression |
| ML | Classification, clustering, regression |

---

## Common Workflows

### Descriptive Statistics

```python
import pandas as pd
df.describe()
```

### Hypothesis Testing

```python
from scipy import stats
stats.ttest_ind(group1, group2)
```

### Correlation Analysis

```python
df.corr(method='pearson')
```

---

## Best Practices

1. Always check data quality first
2. Visualize distributions before testing
3. Report effect sizes alongside p-values
4. Document assumptions and limitations

---

*Skill SKILL-SDR-010 | Statistical Analysis*
