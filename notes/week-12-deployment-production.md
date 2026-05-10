# Week 12 — Deployment & Production

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Multi-stage Dockerfile, ACR build, Container Apps env, ingress, scale rules, Managed Identity._

## Final Architecture
```
[Client] → [Container Apps Ingress] → [DocumentQA.API container]
                                          ↓
                          [Azure OpenAI] [Azure AI Search] [Document Intelligence]
                                          ↓
                                  [Application Insights]
```

## Live URLs
- App: https://___
- Swagger: https://___/swagger
- App Insights workbook: ___

## CI/CD
- Pipeline: `azure-pipelines.yml`
- Trigger: push to `main`
- Build → test → image push → container app update

## Cost & Scale
- Min replicas: 1
- Max replicas: 10
- Scale rule: HTTP concurrency 50
- Daily cost (steady state): $ ___

## Security Checklist
- [ ] Managed Identity for Azure OpenAI / Search
- [ ] No secrets in source or env vars (Key Vault references)
- [ ] Rate limiting enabled
- [ ] HTTPS-only
- [ ] Auth on `/api/*` (API key or OAuth)

## Demo
_Link to recorded demo video (3-5 min)._

## Gotchas
- 

## Resources Used
- [ ] [Deploy to Container Apps](https://learn.microsoft.com/en-us/azure/container-apps/quickstart-portal)
- [ ] [Azure DevOps Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/)

## Feynman Test
> 

## Final Reflection
_What worked, what I'd change, what's next._

> 
