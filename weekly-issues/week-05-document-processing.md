# Week 5: Document Processing

## 🎯 Goal
Extract clean text from PDFs using Azure Document Intelligence and chunk it intelligently.

## ⏱️ Time Budget
- Target: 10-11 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Microsoft Learn — Azure Document Intelligence](https://learn.microsoft.com/en-us/training/modules/process-images-with-azure-document-intelligence/) (1.5 hr)
- [ ] [Document Intelligence Overview](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/overview)
- [ ] Read about chunking strategies (fixed, semantic, recursive, overlap)

## 🛠️ Hands-On
- [ ] Deploy Azure Document Intelligence resource
- [ ] Upload a sample PDF via REST/Postman → inspect output
- [ ] In `code/month-2-rag-pipeline/` create C# console app
- [ ] Implement `PdfReader` using Document Intelligence SDK
- [ ] Implement `TextChunker` (512-token chunks, 50-token overlap)
- [ ] Process 5 sample PDFs

## ✅ Success Criteria
- [ ] Chunks consistently sized (verified with tokenizer)
- [ ] Metadata preserved (doc name, page #)
- [ ] Output saved as JSON

## 📦 Deliverable
- [ ] `notes/week-05-document-processing.md`
- [ ] Sample chunked output in repo

## 🐍 Python-Lite (Optional, 1 hr)
- [ ] Run [python-side/01-syntax-basics.ipynb](../python-side/01-syntax-basics.ipynb)
