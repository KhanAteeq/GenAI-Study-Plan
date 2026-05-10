# Week 11 — Evaluation & Monitoring

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_LLM-as-judge for relevance/groundedness; latency budgets; cost per query._

## Test Set (20-30 questions)
| # | Question | Expected | Got | Relevance (1-5) | Grounded? |
|---|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |

## Aggregate Results
- Avg relevance: ___
- Groundedness rate: ___ %
- p95 latency: ___ ms
- Avg cost / query: $ ___

## Code / Examples
```csharp
_telemetry.TrackEvent("QueryExecuted",
  new() { ["topK"] = topK.ToString() },
  new() { ["latency_ms"] = sw.ElapsedMilliseconds, ["confidence"] = result.Confidence });
```

## Optimizations Applied
- [ ] LRU cache for repeat queries
- [ ] Parallel retrieval
- [ ] Tuned chunk size
- [ ] Batched embeddings

## Gotchas
- 

## Resources Used
- [ ] [App Insights with .NET](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core)

## Feynman Test
> 

## Open Questions
- [ ] 
