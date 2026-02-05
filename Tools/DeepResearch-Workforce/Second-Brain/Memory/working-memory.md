# Working Memory Schema

> **Session State Management for Research Operations**

---

## Memory Keys

```json
{
  "session": {
    "id": "string",
    "started_at": "ISO8601",
    "research_mode": "quick|standard|deep|enterprise"
  },
  "query": {
    "original": "string",
    "clarified": "string",
    "confidence": 0.0-1.0,
    "focus_areas": ["array"]
  },
  "sources": {
    "academic": [],
    "technical": [],
    "web": [],
    "verified_count": 0
  },
  "findings": {
    "claims": [],
    "evidence": [],
    "contradictions": [],
    "gaps": []
  },
  "synthesis": {
    "themes": [],
    "patterns": [],
    "confidence": 0.0-1.0
  },
  "quality": {
    "coverage_score": 0.0-1.0,
    "verification_score": 0.0-1.0,
    "synthesis_score": 0.0-1.0,
    "eo_score": 0.0-1.0
  }
}
```

---

*Working Memory v1.0 | DeepResearch-Workforce*
