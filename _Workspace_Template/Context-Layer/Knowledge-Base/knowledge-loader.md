# Knowledge Loader - KB Integration for Workers

> **_Workspace_Template** | Context-Layer | vnBuilderProMax v2.3.3

---

## Overview

Hướng dẫn Workers cách load và sử dụng Knowledge-Base trong quá trình thực thi.

---

## Knowledge-Base Structure

| Type | Path | Prefix | Purpose |
|------|------|--------|---------|
| **PLAYBOOKS** | `PLAYBOOKS/` | PB-XXX | Strategic protocols, checklists |
| **SKILLS** | `SKILLS/` | SK-XXX | Technical implementation guides |
| **EXPERIENCE** | `EXPERIENCE/` | EXP-XXX | Curated successful patterns from Outputs |

---

## Loading Logic

```
ON Worker_Init:
    
    1. READ knowledge-base-index.json
    
    2. GET worker_tier from context
    
    3. LOAD KB items based on tier_access:
        a. LOAD playbooks assigned to tier
        b. LOAD skills assigned to tier
        c. IF tier has experience_access:
           LOAD relevant experience files
    
    4. INJECT KB context into worker prompt
```

---

## Worker KB Access Matrix

| Tier | PLAYBOOKS | SKILLS | EXPERIENCE | Write Access |
|------|-----------|--------|------------|--------------|
| T1 | PB-001, PB-002, PB-008 | SK-001, SK-003 | ❌ | ❌ |
| T2 | PB-001, PB-004 | SK-001, SK-002, SK-003 | ❌ | ❌ |
| T3 | PB-003, PB-005-008 | SK-004 to SK-008 | ✅ ALL | ❌ |
| T4 | PB-002, PB-008 | SK-009, SK-010 | ❌ | ❌ |
| T5 | PB-002 | SK-010 | ❌ | ❌ |
| T6 | PB-007 | SK-008 | ✅ | ✅ Write EXP |

---

## Context Injection Format

```xml
<knowledge_base>
  <playbooks>
    <playbook id="PB-001" name="ContentBriefProtocol">
      [Content of PB-001-ContentBriefProtocol.md]
    </playbook>
    ...
  </playbooks>
  
  <skills>
    <skill id="SK-001" name="KeywordEntityResearch">
      [Content of SK-001-KeywordEntityResearch.md]
    </skill>
    ...
  </skills>
  
  <experience>
    <exp id="EXP-001" domain="legal">
      [Content of EXP-001-TexasLegalContent.md]
    </exp>
    ...
  </experience>
</knowledge_base>
```

---

## Usage in Workers

### Reading KB

```
READ playbook PB-001:
    FILE: Knowledge-Base/PLAYBOOKS/PB-001-ContentBriefProtocol.md
    INJECT: into worker context
    
READ skill SK-004:
    FILE: Knowledge-Base/SKILLS/SK-004-HumanFirstCopywriting.md
    APPLY: to content generation
```

### Learning from Experience

```
IF worker in Tier3 (Content):
    READ all EXP-* files
    EXTRACT patterns matching current topic
    APPLY patterns to generation
```

---

## Auto-Discovery

The `knowledge-base-index.json` supports auto-discovery:

```json
{
  "auto_discovery": true,
  "learning_pipeline": {
    "source": "../../../Outputs/",
    "target": "EXPERIENCE/",
    "trigger": "quality_score >= 90"
  }
}
```

New EXPERIENCE files are automatically indexed when created by the learning pipeline.

---

*knowledge-loader.md | Context-Layer | v2.3.3*
