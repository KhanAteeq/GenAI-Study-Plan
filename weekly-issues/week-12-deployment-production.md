# Week 12: Deployment & Production

## 🎯 Goal
Containerize the app, deploy to Azure Container Apps, automate with CI/CD.

## ⏱️ Time Budget
- Target: 10-12 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Deploy to Azure Container Apps](https://learn.microsoft.com/en-us/azure/container-apps/quickstart-portal)
- [ ] [Azure DevOps Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/)
- [ ] Read about Managed Identity for keyless auth

## 🛠️ Hands-On
- [ ] Write `Dockerfile` (multi-stage build)
- [ ] `docker build` and `docker run` locally — verify
- [ ] Create Azure Container Registry
- [ ] `az acr build` to push image
- [ ] Create Container Apps environment
- [ ] Deploy app with env vars + ingress
- [ ] Configure auto-scaling (HTTP concurrency rule)
- [ ] Switch to Managed Identity (remove API keys)
- [ ] Create `azure-pipelines.yml` (build → test → deploy)
- [ ] Trigger pipeline; verify auto-deploy
- [ ] Set Azure budget alerts

## ✅ Success Criteria — 🏁 MONTH 3 MILESTONE
- [ ] Live URL serving requests
- [ ] CI/CD pipeline green
- [ ] Auto-scale tested with 100 concurrent requests
- [ ] No secrets in source

## 📦 Final Deliverables
- [ ] `deliverables/week-12-deployment-runbook.md`
- [ ] Architecture diagram in `resources/diagrams/`
- [ ] Demo video (3-5 min) showing upload + query flow
- [ ] Update root `README.md` with live URL + final progress numbers
