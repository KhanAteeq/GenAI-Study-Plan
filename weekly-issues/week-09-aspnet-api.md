# Week 9: ASP.NET Core API

## 🎯 Goal
Wrap the RAG pipeline in a clean REST API.

## ⏱️ Time Budget
- Target: 10-12 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [ASP.NET Core Web API best practices](https://learn.microsoft.com/en-us/aspnet/core/web-api/)
- [ ] [Swagger / OpenAPI](https://learn.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger)

## 🛠️ Hands-On
- [ ] `dotnet new webapi -n DocumentQA.API` in `code/month-3-document-qa/`
- [ ] Configure DI for `IEmbeddingService`, `IRAGService`, `IDocumentService`
- [ ] Build `DocumentsController`: upload, list, delete
- [ ] Build `QueryController`: ask question
- [ ] Add global exception middleware
- [ ] Add Swagger UI
- [ ] Write unit tests for services
- [ ] Test end-to-end via Postman

## ✅ Success Criteria
- [ ] All 5 endpoints (`/upload`, `/documents`, `/documents/{id}`, `/query`, `/health`) work
- [ ] Swagger UI loads at `/swagger`
- [ ] At least 5 unit tests passing

## 📦 Deliverable
- [ ] API in `code/month-3-document-qa/`
