# Session Naming Rules

> Dynamic folder naming for research sessions based on task content

---

## Overview

The auto-persistence system v2.0.0 automatically generates session folder names from the research topic, ensuring:

- **Unique folders** for each research task
- **Human-readable** names based on content
- **Chronological ordering** via date prefix
- **No overwrites** of previous sessions

---

## Naming Format

```
{YYYY-MM-DD}_{sanitized_topic}
```

**Example:**

- Input: `"AI in Education: Comprehensive Deep Research (2024-2026)"`
- Output: `2026-01-31_ai_in_education_comprehensive_deep_resea`

---

## Slug Generation Algorithm

### Step-by-Step Transformation

| Step | Transformation | Example |
|------|----------------|---------|
| 1 | Original topic | `AI in Education: Comprehensive Deep Research (2024-2026)` |
| 2 | Lowercase | `ai in education: comprehensive deep research (2024-2026)` |
| 3 | Replace spaces → `_` | `ai_in_education:_comprehensive_deep_research_(2024-2026)` |
| 4 | Remove special chars | `ai_in_education_comprehensive_deep_research_2024_2026` |
| 5 | Collapse multiple `_` | `ai_in_education_comprehensive_deep_research_2024_2026` |
| 6 | Truncate to 50 chars | `ai_in_education_comprehensive_deep_resea` |
| 7 | Add date prefix | `2026-01-31_ai_in_education_comprehensive_deep_resea` |

### Allowed Characters

Only the following characters are preserved:

- Lowercase letters: `a-z`
- Digits: `0-9`
- Underscore: `_`

### Removed Characters

The following are stripped:

- `:` `,` `.` `'` `"` `(` `)` `-` `[` `]` `{` `}` `/` `\` `@` `#` `$` `%` `^` `&` `*`

---

## Collision Handling

If a folder with the same name already exists:

1. Append counter suffix: `_02`, `_03`, etc.
2. Maximum counter: 99
3. If still collision, append timestamp: `_1706687400`

**Example:**

```
PhaseOutputs/
├── 2026-01-31_ai_in_education/         # First run
├── 2026-01-31_ai_in_education_02/      # Second run same day
└── 2026-01-31_ai_in_education_03/      # Third run same day
```

---

## Source Priority

The system extracts the session name from these Memory Bus keys, in order:

| Priority | Key | Description |
|----------|-----|-------------|
| 1 | `research_topic` | Primary topic from phase-01-query |
| 2 | `query.clarified` | Clarified query text |
| 3 | `query.original` | Original user query |
| 4 | (fallback) | `session_{timestamp}` |

---

## Configuration Reference

From `auto-persistence-config.json`:

```json
"session_naming": {
    "enabled": true,
    "source_key": "research_topic",
    "format": "{date}_{slug}",
    "slug_rules": {
        "max_length": 50,
        "lowercase": true,
        "replace_spaces": "_",
        "remove_special_chars": true,
        "allowed_chars": "a-z0-9_"
    },
    "collision_handling": {
        "enabled": true,
        "suffix_format": "_{counter}",
        "max_counter": 99
    }
}
```

---

## Implementation Hook

```python
def generate_session_folder(memory_bus, config):
    """Generate session folder name from research topic."""
    import re
    from datetime import datetime
    
    # Get topic from memory bus
    topic = memory_bus.get('research_topic') or \
            memory_bus.get('query.clarified') or \
            memory_bus.get('query.original') or \
            f"session_{int(datetime.now().timestamp())}"
    
    # Generate slug
    slug = topic.lower()
    slug = slug.replace(' ', '_')
    slug = re.sub(r'[^a-z0-9_]', '', slug)
    slug = re.sub(r'_+', '_', slug)  # Collapse multiple underscores
    slug = slug[:config['slug_rules']['max_length']]
    slug = slug.strip('_')
    
    # Add date prefix
    date_prefix = datetime.now().strftime('%Y-%m-%d')
    session_folder = f"{date_prefix}_{slug}"
    
    # Handle collision
    base_folder = session_folder
    counter = 2
    output_path = config['output_path']
    while os.path.exists(f"{output_path}/{session_folder}"):
        session_folder = f"{base_folder}_{counter:02d}"
        counter += 1
        if counter > config['collision_handling']['max_counter']:
            session_folder = f"{base_folder}_{int(datetime.now().timestamp())}"
            break
    
    # Create folder
    os.makedirs(f"{output_path}/{session_folder}", exist_ok=True)
    
    # Store in memory bus for subsequent phases
    memory_bus['session.folder'] = session_folder
    
    return session_folder
```

---

*Session Naming Rules v2.0.0 | ScholarDeepResearch-Workforce*
