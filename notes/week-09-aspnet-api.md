# Week 9 — ASP.NET Core API

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Controller responsibilities, DI lifetimes, model validation, error middleware, Swagger._

## API Contract
| Verb | Route | Body | Returns |
|---|---|---|---|
| POST | /api/documents/upload | multipart/form-data (file) | { documentId, status } |
| GET  | /api/documents | — | Document[] |
| DELETE | /api/documents/{id} | — | 204 |
| POST | /api/query | { question, topK } | { answer, sources[], confidence } |
| GET  | /api/health | — | { status: "ok" } |

## Code / Examples
```csharp
builder.Services.AddScoped<IRAGService, RAGService>();
builder.Services.AddSingleton(BuildSearchClient(builder.Configuration));
builder.Services.AddSingleton(BuildKernel(builder.Configuration));
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();
```

## Gotchas
- 

## Resources Used
- [ ] [ASP.NET Core Web API](https://learn.microsoft.com/en-us/aspnet/core/web-api/)
- [ ] [Swagger / OpenAPI](https://learn.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger)

## Feynman Test
> 

## Open Questions
- [ ] 
