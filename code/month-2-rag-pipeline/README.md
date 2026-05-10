# Month 2 — RAG Pipeline

**Goal**: Build an end-to-end RAG pipeline that ingests PDFs and answers questions with citations.

## Tech Stack
- .NET 8
- Azure Document Intelligence
- Azure OpenAI Embeddings (text-embedding-3-small)
- Azure AI Search (vector index)
- Microsoft.SemanticKernel

## Components
1. **Ingestion** — PDF → text → chunks → embeddings → Azure AI Search
2. **Cache** — Local embedding cache to cut API costs
3. **Retrieval** — Query → embed → vector search → top-K
4. **Augmentation** — Build prompt with retrieved context
5. **Generation** — GPT-4 answer with source citations

## Status
- [ ] Document ingestion pipeline
- [ ] Embedding cache
- [ ] Vector index in Azure AI Search
- [ ] End-to-end RAG query working
- [ ] Citations in responses
