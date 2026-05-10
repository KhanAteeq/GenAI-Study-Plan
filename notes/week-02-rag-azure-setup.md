# Week 2 — RAG Concepts & Azure Setup

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_What is RAG? Sketch the 6-step flow: Document → Chunk → Embed → Index → Retrieve → Generate._

- 

## Why It Matters
_Why RAG over fine-tuning for the Document QA app?_

- 

## Azure Resources Created
| Resource | Name | Region | Notes |
|---|---|---|---|
| Resource Group | GenAI-Study | | |
| Azure OpenAI | | | GPT-4 + text-embedding-3-small |
| Azure AI Search | | | Standard, semantic ranker on |

> 🔒 Endpoints + keys saved in local `.env` (gitignored).

## Code / Examples
```http
POST https://{resource}.openai.azure.com/openai/deployments/{deployment}/chat/completions?api-version=2024-02-15-preview
api-key: {key}

{ "messages": [{"role":"user","content":"Hello"}], "temperature": 0.7 }
```

## Gotchas
- 

## Resources Used
- [ ] [MS Learn — RAG Concepts](https://learn.microsoft.com/en-us/training/modules/rag-concepts/)
- [ ] [Azure AI Search Vector Overview](https://learn.microsoft.com/en-us/azure/search/vector-search-overview)
- [ ] [Create Azure OpenAI Resource](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource)

## Feynman Test
> 

## Open Questions
- [ ] 
