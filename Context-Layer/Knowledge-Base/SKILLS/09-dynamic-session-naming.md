---
always: false
tier: [1,8]
description: "Generate sanitized session folder names from task context"
core_modules: [MemoryStore]
---

# SKILL: Dynamic Session Naming

> **Purpose**: Generate sanitized session folder names from task context.

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Input** | Task topic string |
| **Output** | Sanitized folder name |
| **Format** | `{YYYY-MM-DD}_{topic_slug}` |

---

## Slug Generation Algorithm

### Step 1: Extract Topic

Extract the research/task topic from:

- User query first sentence
- Memory key `query.topic` or `task.topic`
- First 10 meaningful words

### Step 2: Sanitize

```python
def sanitize_topic(topic: str) -> str:
    # 1. Lowercase
    slug = topic.lower()
    
    # 2. Remove special characters (keep alphanumeric, spaces)
    slug = re.sub(r'[^a-z0-9\s]', '', slug)
    
    # 3. Replace spaces with underscores
    slug = re.sub(r'\s+', '_', slug.strip())
    
    # 4. Remove consecutive underscores
    slug = re.sub(r'_+', '_', slug)
    
    # 5. Truncate to max length
    slug = slug[:50]
    
    # 6. Remove trailing underscores
    slug = slug.rstrip('_')
    
    return slug
```

### Step 3: Generate Folder Name

```python
def generate_session_folder(topic: str) -> str:
    date = datetime.now().strftime('%Y-%m-%d')
    slug = sanitize_topic(topic)
    return f"{date}_{slug}"
```

---

## Examples

| Input Topic | Output Folder |
|-------------|---------------|
| AI in Education (2024-2026) | `2026-01-31_ai_in_education_2024_2026` |
| LLM Progress: Recent Advances | `2026-01-31_llm_progress_recent_advances` |
| What is the state of quantum ML? | `2026-01-31_what_is_the_state_of_quantum_ml` |
| Climate Change & Policy Analysis! | `2026-01-31_climate_change_policy_analysis` |

---

## Collision Handling

If folder already exists:

1. Append counter: `{folder}_001`, `{folder}_002`
2. Or append timestamp: `{folder}_1430` (HHMM)

---

*SKILL v2.0.0 | Dynamic Session Naming | MASDesign-Workforce*
