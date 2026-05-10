# Week 11: Evaluation & Monitoring

## 🎯 Goal
Measure RAG quality and set up production-grade monitoring.

## ⏱️ Time Budget
- Target: 10-11 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Application Insights with .NET](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core)
- [ ] Read about LLM-based evaluation (groundedness, relevance)

## 🛠️ Hands-On
- [ ] Build a 20-30 question test set (with expected answers)
- [ ] Implement `EvaluateQueryAsync` using GPT-4 as judge (relevance 1-5, groundedness, completeness)
- [ ] Run eval, compute averages, log to App Insights
- [ ] Configure App Insights: request latency, vector search latency, LLM latency, error rate, cost/query
- [ ] Build dashboard / workbook in Azure Monitor
- [ ] Add LRU `IMemoryCache` for repeated queries
- [ ] Optimize until p95 latency <2s

## ✅ Success Criteria
- [ ] Average relevance >80%
- [ ] p95 latency <2s
- [ ] Live dashboard with key metrics

## 📦 Deliverable
- [ ] `deliverables/week-11-eval-report.md`
- [ ] Dashboard screenshot
