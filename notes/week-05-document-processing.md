# Week 5 — Document Processing

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Document Intelligence pre-built models, layout vs read, chunking strategies._

- 

## Why It Matters
_"Garbage in = garbage out" for RAG. Clean extraction → better retrieval._

## Chunking Strategy Decisions
| Param | Value | Reason |
|---|---|---|
| Chunk size | 512 tokens | |
| Overlap | 50 tokens | |
| Strategy | recursive | |

## Code / Examples
```csharp
var client = new DocumentIntelligenceClient(endpoint, credential);
var op = await client.AnalyzeDocumentAsync(WaitUntil.Completed, "prebuilt-read", uri);
var text = op.Value.Content;
```

## Gotchas
- 

## Resources Used
- [ ] [MS Learn — Document Intelligence](https://learn.microsoft.com/en-us/training/modules/process-images-with-azure-document-intelligence/)
- [ ] [Document Intelligence Overview](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/overview)

## Feynman Test
> 

## Open Questions
- [ ] 
