# Reference Guidelines for Workforce Creation

> **vnBuilderProMax v2.3.4** | Hướng dẫn tham chiếu cấu trúc

---

## Structural Reference: SEO-AEO-GEO-EEAT-BlogWriter

> [!IMPORTANT]  
> BlogWriter là tham chiếu **CẤU TRÚC DUY NHẤT**. Không được sao chép nội dung gốc.

---

## ✅ ALLOWED - Structural Reference

| Element | Source | Example |
| ------- | ------ | ------- |
| Directory layout | `Workers/Tier1-6/` | 6 tiers with W01-W22 |
| File naming | `W01-*.md` pattern | `W01-YourWorker.md` |
| Autonomous-Core | 9 core files | Same file names, custom content |
| Context-Layer | KB, CoreModules, Second-Brain | Same structure, domain content |
| Team Orchestration | 15 coordination files | Same patterns, custom config |

---

## ❌ PROHIBITED - Content Copying

| Do NOT Copy | Why |
| ----------- | --- |
| SEO/AEO/GEO strategies | Domain-specific to BlogWriter |
| EEAT compliance content | Blog-specific standards |
| Worker prompt content | Must be custom for your domain |
| Knowledge-Base entries | Must be domain-specific |
| Playbook/Skill details | Content is blog-focused |

---

## How to Use BlogWriter Reference

### Step 1: Analyze Structure

```powershell
# View directory structure
tree /F "D:\BuilderPro\_vnBuilderPro-MAS2026\WorkForce_Example\SEO-AEO-GEO-EEAT-BlogWriter"
```

### Step 2: Extract Patterns Only

- **File count per tier** (e.g., Tier1 has 4 workers: W01-W04)
- **File naming conventions** (e.g., `W01-ContentStrategyResearch.md`)
- **Subdirectory organization** (e.g., `Context-Layer/Knowledge-Base/PLAYBOOKS/`)

### Step 3: Create YOUR Domain Content

- Replace all SEO/AEO/GEO references with YOUR domain terminology
- Write worker prompts specific to YOUR use case
- Generate Knowledge-Base entries for YOUR field

---

## Example: Creating a New Workforce

**Source (BlogWriter):**

```
Workers/Tier1-Strategy/W01-ContentStrategyResearch.md
```

**Your Workforce (e.g., DataAnalytics):**

```
Workers/Tier1-Strategy/W01-DataStrategyResearch.md
```

- ✅ Same file location: `Workers/Tier1-Strategy/`
- ✅ Same naming pattern: `W01-*.md`
- ❌ Different content: Data analytics vs. SEO content

---

## Key Principle

```
Structure = COPY
Content = CREATE
```

---

*Reference Guidelines v1.0 | vnBuilderProMax v2.3.4*
