# Week 6 — Embeddings & Caching

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Embedding model trade-offs, batch APIs, cache key design._

- 

## Why It Matters
_Embeddings cost money per token; caching cuts re-runs to near-zero._

## Cost Tracking
| Run | Chunks | API calls | $ |
|---|---|---|---|
| First run | | | |
| Second run (cached) | | | |

## Code / Examples
```csharp
public class EmbeddingCache
{
    private readonly Dictionary<string, float[]> _cache = new();

    public bool TryGet(string text, out float[] vec)
        => _cache.TryGetValue(Hash(text), out vec);

    public void Set(string text, float[] vec)
        => _cache[Hash(text)] = vec;

    static string Hash(string s)
        => Convert.ToHexString(SHA256.HashData(Encoding.UTF8.GetBytes(s)));
}
```

## Gotchas
- 

## Resources Used
- [ ] [Azure OpenAI Embeddings](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/understand-embeddings)

## Feynman Test
> 

## Open Questions
- [ ] 
