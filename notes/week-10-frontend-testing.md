# Week 10 — Frontend (Optional) & Integration Testing

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Path Chosen
- [ ] **A** — API hardening (tests, validation, rate limiting, load test)
- [ ] **B** — React UI

## Concept
_WebApplicationFactory test pattern, FluentValidation, rate limiting middleware._

## Code / Examples
```csharp
// Integration test
public class QueryEndpointTests : IClassFixture<WebApplicationFactory<Program>>
{
    private readonly HttpClient _client;
    public QueryEndpointTests(WebApplicationFactory<Program> f) => _client = f.CreateClient();

    [Fact]
    public async Task Query_Returns200_WithAnswer()
    {
        var resp = await _client.PostAsJsonAsync("/api/query",
            new { question = "What is RAG?", topK = 5 });
        resp.EnsureSuccessStatusCode();
    }
}
```

## Load-Test Results
| Concurrency | p50 ms | p95 ms | Errors |
|---|---|---|---|
| 10 | | | |
| 50 | | | |
| 100 | | | |

## Gotchas
- 

## Resources Used
- [ ] [Integration tests in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests)

## Feynman Test
> 

## Open Questions
- [ ] 
