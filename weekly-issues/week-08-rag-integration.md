# Week 8: RAG Integration

## 🎯 Goal
Wire everything together into a complete RAG pipeline that answers questions with citations.

## ⏱️ Time Budget
- Target: 10-12 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [RAG Advanced Concepts](https://learn.microsoft.com/en-us/training/modules/rag-advanced-concepts/)
- [ ] Study augmentation & citation patterns
- [ ] Read about reranking strategies

## 🛠️ Hands-On
- [ ] Create `RAGPipeline` class: embed query → search → augment → generate
- [ ] Use Semantic Kernel for the LLM call
- [ ] Build prompt with retrieved context + system instructions
- [ ] Format response with source citations (doc name, page)
- [ ] Handle edge cases: no results, low confidence
- [ ] Test on 10 questions across indexed docs

## ✅ Success Criteria — 🏁 MONTH 2 MILESTONE
- [ ] 8/10 answers are accurate
- [ ] All answers include citations
- [ ] Response time <3 sec

## 📦 Deliverable
- [ ] Working RAG in `code/month-2-rag-pipeline/`
- [ ] `deliverables/week-08-rag-eval.md` with test queries + results
