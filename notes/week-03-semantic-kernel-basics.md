# Week 3 — Semantic Kernel Basics

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Kernel, Services, Plugins, Functions — what is each and how do they fit?_

- 

## Why It Matters
_Why use Semantic Kernel instead of calling the OpenAI SDK directly?_

- 

## Code / Examples
```csharp
var builder = Kernel.CreateBuilder();
builder.AddAzureOpenAIChatCompletion(
    deploymentName: "gpt-4",
    endpoint: Environment.GetEnvironmentVariable("AZURE_OPENAI_ENDPOINT"),
    apiKey:   Environment.GetEnvironmentVariable("AZURE_OPENAI_KEY"));
var kernel = builder.Build();

var reply = await kernel.InvokePromptAsync("Explain RAG in one sentence");
Console.WriteLine(reply);
```

```csharp
public class MathPlugin
{
    [KernelFunction("Add"), Description("Adds two numbers")]
    public int Add(int a, int b) => a + b;
}
kernel.ImportPluginFromType<MathPlugin>("math");
```

## Gotchas
- 

## Resources Used
- [ ] [MS Learn — Getting started with SK](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-get-started/)
- [ ] [SK Quick Start](https://learn.microsoft.com/en-us/semantic-kernel/get-started/quick-start-guide)
- [ ] [SK .NET samples](https://github.com/microsoft/semantic-kernel/tree/main/dotnet/samples)

## Feynman Test
> 

## Open Questions
- [ ] 
