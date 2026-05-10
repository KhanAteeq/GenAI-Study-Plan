# Week 3: Semantic Kernel Basics

## 🎯 Goal
Build a working .NET console app that talks to Azure OpenAI through Semantic Kernel.

## ⏱️ Time Budget
- Target: 10-12 hours
- Actual: ___

## 📖 Learning Tasks
- [ ] [Microsoft Learn — Getting started with Semantic Kernel](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-get-started/) (1.5 hr)
- [ ] [Semantic Kernel Quick Start](https://learn.microsoft.com/en-us/semantic-kernel/get-started/quick-start-guide)
- [ ] Browse [SK .NET samples](https://github.com/microsoft/semantic-kernel/tree/main/dotnet/samples)
- [ ] Understand: Kernel, Services, Plugins, Functions

## 🛠️ Hands-On
- [ ] `dotnet new console -n Chatbot` in `code/month-1-chatbot/`
- [ ] Add NuGet: `Microsoft.SemanticKernel`
- [ ] Initialize Kernel with Azure OpenAI
- [ ] Send 5 different prompts and log responses
- [ ] Build `MathPlugin` with `Add`, `Subtract`, `Multiply` (auto function calling)
- [ ] Verify LLM auto-invokes the plugin

## ✅ Success Criteria
- [ ] App compiles and runs
- [ ] LLM correctly calls `MathPlugin.Add(5, 3)` when asked
- [ ] No hardcoded keys in source (use env vars / user-secrets)

## 📦 Deliverable
- [ ] Working code in `code/month-1-chatbot/`
- [ ] `notes/week-03-semantic-kernel-basics.md`
