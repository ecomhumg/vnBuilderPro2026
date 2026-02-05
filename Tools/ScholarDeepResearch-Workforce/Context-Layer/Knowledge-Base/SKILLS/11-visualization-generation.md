# Visualization Generation

> **Skill ID**: SKILL-SDR-011
> **Tools**: code_interpreter, image generation

---

## Overview

Skills for creating data visualizations and visual reports.

---

## Visualization Library

| Type | Tool | Use Case |
|------|------|----------|
| Line/Bar/Scatter | matplotlib | Standard charts |
| Heatmaps | seaborn | Correlation matrices |
| Network | networkx | Relationships |
| Custom | image generation | Complex diagrams |

---

## Code Templates

### Line Plot

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(10, 6))
plt.plot(x, y)
plt.xlabel('Label')
plt.ylabel('Value')
plt.title('Title')
plt.savefig('plot.png', dpi=300)
```

### Heatmap

```python
import seaborn as sns
sns.heatmap(data, annot=True, cmap='coolwarm')
```

---

## Quality Standards

- Resolution: ≥300 DPI
- Labels: Clear, descriptive
- Colors: Accessible, colorblind-safe
- Legend: Present when needed

---

*Skill SKILL-SDR-011 | Visualization Generation*
