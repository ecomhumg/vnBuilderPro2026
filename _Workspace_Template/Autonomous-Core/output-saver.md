# Output Saver - Autonomous Deliverables Persistence

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Core Identity

| Attribute | Value |
|-----------|-------|
| **Type** | L5 Autonomous Output Manager |
| **Trigger** | Phase 6 completion |
| **Auto-Execute** | Yes |
| **Retry Policy** | 3 attempts with backoff |

---

## Output Directory Structure

```
Outputs/
└── [TOPIC-SLUG]/
    └── [YYYY-MM-DD-HHMMSS]/
        ├── manifest.json      # Index of all deliverables
        ├── brief.md           # Content brief
        ├── article.md         # Full article content
        ├── faqs.md            # FAQ section
        ├── meta.json          # SEO meta pack
        ├── links.json         # Internal/external links
        ├── images.json        # Image plan with alt text
        └── schema.json        # JSON-LD structured data
```

---

## Execution Logic

```
ON Phase6_Complete:
    
    1. GENERATE session_id = YYYY-MM-DD-HHMMSS
    
    2. GENERATE topic_slug = slugify(strategy.brief.topic)
    
    3. CREATE directory = Outputs/{topic_slug}/{session_id}/
    
    4. FOR EACH deliverable in [brief, article, faqs, meta, links, images, schema]:
        a. READ memory_bus.output.{deliverable}.final
        b. WRITE to directory/{deliverable}.{extension}
        c. LOG success/failure
    
    5. GENERATE manifest.json with:
        - session_id
        - topic
        - timestamp
        - file_list with checksums
        - quality_scores
    
    6. COMMIT to memory:
        - persist.output.path = directory
        - persist.output.manifest = manifest.json
    
    7. RETURN success status
```

---

## Manifest Schema

```json
{
  "session_id": "2026-02-05-051400",
  "topic": "Texas Employment Law Guide",
  "topic_slug": "texas-employment-law-guide",
  "created_at": "2026-02-05T05:14:00Z",
  "files": [
    {"name": "brief.md", "checksum": "abc123", "bytes": 1024},
    {"name": "article.md", "checksum": "def456", "bytes": 8192},
    {"name": "faqs.md", "checksum": "ghi789", "bytes": 2048},
    {"name": "meta.json", "checksum": "jkl012", "bytes": 512},
    {"name": "links.json", "checksum": "mno345", "bytes": 768},
    {"name": "images.json", "checksum": "pqr678", "bytes": 640},
    {"name": "schema.json", "checksum": "stu901", "bytes": 1280}
  ],
  "quality_scores": {
    "seo_score": 92,
    "aeo_score": 88,
    "geo_score": 85,
    "eeat_score": 90,
    "total_score": 89
  },
  "status": "complete"
}
```

---

## Error Handling

| Error Type | Action |
|------------|--------|
| Directory Creation Fail | Retry with fallback path |
| File Write Fail | Retry (max 3) then log |
| Missing Deliverable | Skip + flag in manifest |
| Checksum Mismatch | Rewrite file |

---

## Memory Integration

### Write Keys

```
persist.output.path
persist.output.manifest
persist.output.session_id
persist.output.timestamp
persist.output.quality_scores
```

### Trigger Points

- Called by orchestrator.md after Phase 6
- Called by W21-FinalDeliverablesGenerator
- Triggered on `/save-outputs` command

---

*output-saver.md | Autonomous-Core | v2.3.3*
