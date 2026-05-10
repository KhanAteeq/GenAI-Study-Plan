# Week 6: Embeddings & Caching

## 🎯 Goal
Generate embeddings for chunks at scale, with caching to control cost.

## ⏱️ Time Budget
- Target: 10-11 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Azure OpenAI Embeddings](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/understand-embeddings)
- [ ] Compare text-embedding-3-small vs -large (cost vs quality)
- [ ] Read about batch embedding APIs

## 🛠️ Hands-On
- [ ] Generate embeddings for 10+ documents (100+ chunks)
- [ ] Implement `EmbeddingCache` keyed by content hash
- [ ] Batch chunks per API call to minimize cost
- [ ] Persist cache to disk (JSON)
- [ ] Verify cache hits speed up second run

## ✅ Success Criteria
- [ ] Embeddings are 1536-dim float arrays
- [ ] Cache hit rate >90% on second run
- [ ] Cost logged per run

## 📦 Deliverable
- [ ] Cached embeddings file committed (sample subset only)
- [ ] `notes/week-06-embeddings-caching.md`

## 🐍 Python-Lite (Optional, 1 hr)
- [ ] Run [python-side/02-openai-api.ipynb](../python-side/02-openai-api.ipynb) — same call in C# vs Python
