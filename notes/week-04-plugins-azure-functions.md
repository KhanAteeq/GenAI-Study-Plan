# Week 4 — Plugins & Azure Functions

> **Started**: _YYYY-MM-DD_
> **Issue**: #_N_
> **Hours spent**: ___

---

## Concept
_Auto function calling, ChatHistory, Azure Functions HTTP trigger lifecycle._

- 

## Why It Matters
_Why deploy as Azure Functions vs always-on App Service for a chatbot?_

- 

## Code / Examples
```csharp
[Function("Chat")]
public async Task<HttpResponseData> Chat(
    [HttpTrigger(AuthorizationLevel.Anonymous, "post")] HttpRequestData req)
{
    var body = await req.ReadFromJsonAsync<ChatRequest>();
    var reply = await _kernel.InvokePromptAsync(body.Message);
    var resp = req.CreateResponse(HttpStatusCode.OK);
    await resp.WriteAsJsonAsync(new { reply = reply.ToString() });
    return resp;
}
```

## Deployment Notes
- Function App name: 
- URL: 
- Application Insights: 

## Gotchas
- 

## Resources Used
- [ ] [MS Learn — SK Plugins](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-plugins/)
- [ ] [Azure Functions .NET Quickstart](https://learn.microsoft.com/en-us/azure/azure-functions/functions-get-started)
- [ ] [App Insights for .NET](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core)

## Feynman Test
> 

## Open Questions
- [ ] 
