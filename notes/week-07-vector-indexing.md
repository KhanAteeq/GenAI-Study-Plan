# Week 7 — Vector Indexing

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_HNSW vs DiskANN vs flat. Hybrid search. Semantic ranker._

- 

## Index Schema
```json
{
  "name": "documents",
  "fields": [
    { "name": "id", "type": "Edm.String", "key": true },
    { "name": "title", "type": "Edm.String" },
    { "name": "content", "type": "Edm.String", "searchable": true },
    {
      "name": "vector",
      "type": "Collection(Edm.Single)",
      "searchable": true,
      "dimensions": 1536,
      "vectorSearchProfile": "default"
    }
  ]
}
```

## Code / Examples
```csharp
var batch = IndexDocumentsBatch.Upload(chunks);
await searchClient.IndexDocumentsAsync(batch);
```

## Gotchas
- 

## Resources Used
- [ ] [SK Vector Store Connectors](https://learn.microsoft.com/en-us/semantic-kernel/concepts/vector-store-connectors/)
- [ ] [Create Vector Index](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-create-index)
- [ ] [Semantic Ranker](https://learn.microsoft.com/en-us/azure/search/semantic-search-overview)

## Feynman Test
> 

## Open Questions
- [ ] 
