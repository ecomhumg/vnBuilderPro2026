# Goal Manager

> **{WorkforceName}-Workforce** | Autonomous-Core
> **Standard**: vnBuilderProMax v2.3.3

---

## Purpose

Manage high-level goals and decompose into actionable tasks.

---

## Goal Hierarchy

```yaml
levels:
  L1: Mission (workforce purpose)
  L2: Objectives (session goals)
  L3: Tasks (tier deliverables)
  L4: Actions (worker operations)
```

---

## Goal Processing

```yaml
process:
  1. Parse Input:
     - Extract user intent
     - Identify constraints
     - Set success criteria
  
  2. Decompose:
     - Break into objectives
     - Map to worker tasks
     - Define dependencies
  
  3. Prioritize:
     - Apply MoSCoW
     - Sequence by dependency
     - Allocate resources
  
  4. Track:
     - Monitor completion
     - Update status
     - Report progress
```

---

## Domain-Specific Goals

| Goal Type | Workers |
|-----------|---------|
| {GoalType1} | W01-W04 |
| {GoalType2} | W02, W05, W09 |
| {GoalType3} | W12 |
| {GoalType4} | W19, W20 |

---

*goal-manager.md | Autonomous-Core | v2.3.3*
