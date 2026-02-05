# Debugging Strategies

> **Troubleshooting MAS Issues**

---

## Debug Hierarchy

1. **Check Inputs** - Is the data correct?
2. **Check Triggers** - Did agents fire?
3. **Check Memory** - Are keys populated?
4. **Check Outputs** - What was produced?
5. **Check Logs** - What happened?

---

## Common Issues

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Agent not firing | Missing trigger | Check event/condition |
| Wrong output | Bad input | Validate inputs |
| Timeout | Processing stuck | Add logging, check loops |
| Low quality | Pattern mismatch | Review pattern selection |
| Missing data | Key not written | Trace write path |

---

## Debugging Tools

1. **Memory Bus Dump** - Show all current keys
2. **Execution Trace** - Log agent activations
3. **Quality Breakdown** - Per-dimension scores
4. **Pattern Report** - Which patterns used

---

## Escalation Path

```
Self-diagnose → Check logs → Review traces → Isolate component → Manual test → Human review
```

---

*Debugging Strategies v1.0 | MASDesign-Workforce*
