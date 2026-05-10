# Month 3 — Production Document QA App

**Goal**: Wrap the RAG pipeline in a production-grade ASP.NET Core API, containerize, deploy to Azure Container Apps, with CI/CD and monitoring.

## Tech Stack
- ASP.NET Core 8 Web API
- Docker
- Azure Container Registry + Container Apps
- Azure DevOps Pipelines
- Application Insights
- (Optional) React + Tailwind frontend

## API Endpoints
```
POST   /api/documents/upload
GET    /api/documents
DELETE /api/documents/{id}
POST   /api/query
GET    /api/health
```

## Status
- [ ] REST API with all endpoints
- [ ] Swagger / OpenAPI docs
- [ ] Dockerfile + local container test
- [ ] Deployed to Azure Container Apps
- [ ] CI/CD pipeline (Azure DevOps)
- [ ] Auto-scaling configured
- [ ] App Insights dashboard
- [ ] Eval report (>80% relevance, <2s latency)
- [ ] Demo video
