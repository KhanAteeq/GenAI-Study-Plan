# Week 8 — RAG Integration

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Augmentation pattern: System + Retrieved context + User question → Answer with citations._

## Prompt Template
```
System: You are a helpful assistant. Answer ONLY using the provided context.
        If the context is insufficient, say "I don't know."

Context:
[1] {doc1.title} (p.{doc1.page}): {doc1.content}
[2] {doc2.title} (p.{doc2.page}): {doc2.content}
[3] {doc3.title} (p.{doc3.page}): {doc3.content}

Question: {user_query}

Answer (cite sources as [1], [2], [3]):
```

## Eval Results (10 questions)
| # | Question | Accurate? | Latency (ms) |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| ... | | | |

## Code / Examples
```csharp
var qVec = await _embed.GenerateAsync(query);
var hits = await _search.SearchAsync(qVec, top: 5);
var prompt = BuildPrompt(query, hits);
var answer = await _kernel.InvokePromptAsync(prompt);
```

## Gotchas
- 

## Resources Used
- [ ] [RAG Advanced Concepts](https://learn.microsoft.com/en-us/training/modules/rag-advanced-concepts/)

## Feynman Test
> 

## Open Questions
- [ ] 
