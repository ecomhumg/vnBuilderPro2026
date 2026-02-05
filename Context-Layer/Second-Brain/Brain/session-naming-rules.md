# Session Naming Rules

> **Purpose**: Rules for generating dynamic session folder names from task context.

---

## Naming Format

```
{YYYY-MM-DD}_{sanitized_topic}
```

### Examples

| Task Topic | Session Folder |
|------------|----------------|
| AI in Education (2024-2026) | `2026-01-31_ai_in_education_2024_2026` |
| LLM Progress: Recent Advances | `2026-01-31_llm_progress_recent_advances` |
| What is quantum ML? | `2026-01-31_what_is_quantum_ml` |

---

## Sanitization Rules

1. **Lowercase**: Convert all characters to lowercase
2. **Spaces → Underscores**: Replace spaces with `_`
3. **Remove Special Chars**: Remove `()[]{}:;,.!?@#$%^&*`
4. **Max Length**: Truncate to 50 characters
5. **Trim**: Remove leading/trailing underscores

---

## Topic Extraction

Extract topic from first available source:

1. `query.topic` memory key
2. `task.topic` memory key
3. First 10 meaningful words from user query
4. `input.user_request` summary

---

## Collision Handling

| Scenario | Action |
|----------|--------|
| Folder exists | Append counter: `_001`, `_002` |
| Same-day duplicate | Append time: `_1430` (HHMM) |

---

*Session Naming Rules v2.0.0 | MASDesign-Workforce*
