# Orchestration Lessons

> **Wisdom from Team Coordination Experience**

---

## Lessons Learned

### 1. Tier Boundaries Matter
Workers within a tier run parallel, tiers run sequential.
- Clear boundaries reduce coordination bugs
- Shared memory keys need careful ownership

### 2. Timeouts Are Your Friend
- Set reasonable timeouts
- Have fallback strategies
- Log timeout occurrences for tuning

### 3. Quality Gates Pay Off
- Early quality checks catch 80% of issues
- Multiple gates with lower thresholds beat one high gate
- Gate failures should be informative

### 4. Handoff Contracts Are Essential
- Document what crosses worker boundaries
- Validate on receive, not just send
- Version your contracts

---

## Coordination Pitfalls

| Pitfall | Solution |
|---------|----------|
| Race conditions | Use memory bus properly |
| Deadlocks | Clear dependency ordering |
| Starvation | Fair scheduling |
| Cascade failures | Circuit breakers |

---

*Orchestration Lessons v1.0 | MASDesign-Workforce*
