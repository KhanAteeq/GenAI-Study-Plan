# Month 1 — Semantic Kernel Chatbot

**Goal**: Build a .NET chatbot using Semantic Kernel + Azure OpenAI with custom plugins, deployed to Azure Functions.

## Tech Stack
- .NET 8
- Microsoft.SemanticKernel
- Azure OpenAI (GPT-4)
- Azure Functions (HTTP trigger)
- Application Insights

## Build Steps
1. `dotnet new console`
2. Add Semantic Kernel + Azure OpenAI
3. Implement `MathPlugin` and `WeatherPlugin`
4. Wrap in Azure Function
5. Deploy with `func azure functionapp publish`

## Demo
_Add screenshot/GIF after deploy._

## Status
- [ ] Local chatbot working
- [ ] Plugins auto-called by LLM
- [ ] Deployed to Azure Functions
- [ ] App Insights logging
