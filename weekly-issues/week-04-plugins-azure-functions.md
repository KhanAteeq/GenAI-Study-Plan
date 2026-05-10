# Week 4: Plugins & Azure Functions

## 🎯 Goal
Add advanced plugins to the chatbot and deploy it as an Azure Function with logging.

## ⏱️ Time Budget
- Target: 10-12 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Microsoft Learn — Creating plugins with Semantic Kernel](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-plugins/)
- [ ] [Semantic Kernel Memory](https://learn.microsoft.com/en-us/semantic-kernel/concepts/memory/)
- [ ] [Azure Functions .NET Quickstart](https://learn.microsoft.com/en-us/azure/azure-functions/functions-get-started)

## 🛠️ Hands-On
- [ ] Add `WeatherPlugin` (mock API or real call)
- [ ] Add `ChatHistory` for multi-turn context
- [ ] Convert chatbot to Azure Function (HTTP trigger)
- [ ] Wire up Application Insights
- [ ] Deploy: `func azure functionapp publish <name>`
- [ ] Test deployed endpoint via Postman

## ✅ Success Criteria
- [ ] POST to Azure Function returns a chatbot response
- [ ] Both plugins called appropriately
- [ ] Logs visible in Application Insights

## 📦 Deliverable — 🏁 MONTH 1 MILESTONE
- [ ] Deployed Function URL recorded in `deliverables/week-04-chatbot-demo.md`
- [ ] Screenshot/GIF of working chatbot
