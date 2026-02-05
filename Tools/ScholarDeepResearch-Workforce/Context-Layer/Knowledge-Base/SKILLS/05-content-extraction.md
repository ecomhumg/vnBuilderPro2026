# Content Extraction

> **Skill ID**: SKILL-SDR-005
> **Tools**: extractUrl

---

## Overview

Universal content extraction from URLs and files.

---

## Tool Usage

### extractUrl

- **Purpose**: Read links and files of any type
- **Capabilities**: Web pages, PDFs, documents
- **Parameters**: url

---

## Supported Formats

| Format | Extraction Type |
|--------|-----------------|
| HTML | Text content |
| PDF | Text + layout |
| DOCX | Text + structure |
| TXT | Raw text |
| CSV | Tabular data |

---

## Extraction Strategies

1. **Direct URL**: Pass complete URL to extractUrl
2. **Dataset Links**: Process file URLs for data
3. **Fallback**: Use platform-specific fulltext tools if extractUrl fails

---

## Error Handling

| Error | Resolution |
|-------|------------|
| 403 Forbidden | Try platform-specific tool |
| 404 Not Found | Search for alternate source |
| Paywall | Flag for user intervention |
| Timeout | Retry with shorter content |

---

*Skill SKILL-SDR-005 | Content Extraction*
