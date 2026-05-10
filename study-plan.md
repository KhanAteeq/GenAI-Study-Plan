# 📚 Complete 3-Month GenAI Engineer Study Plan

## 📋 Overview

- **Goal**: Build a production-ready **Document QA System** using .NET + Azure
- **Duration**: 3 months (12 weeks) at 10-15 hours/week
- **Total Hours**: ~120-180 hours
- **Final Project**: Upload PDFs → System extracts, indexes, and answers questions with AI

---

# 🔵 MONTH 1: GenAI Foundations + Semantic Kernel (Weeks 1-4)

## Week 1-2: LLM Fundamentals & Azure Setup (15 hours)

### 📖 Topics to Learn (8 hours)

#### 1. What is an LLM? (2 hours)
- **What to Learn**:
  - What are Large Language Models (GPT-4, Claude)
  - How LLMs work: tokens, tokenization, token limits
  - Temperature and Top-P (control randomness in responses)
  - Max tokens vs. context window
  - Difference between GPT-3.5 vs GPT-4 (cost/performance)
- **Resources**:
  - Microsoft Learn: [Understand Generative AI](https://learn.microsoft.com/en-us/training/modules/fundamentals-generative-ai/) (30 min)
  - OpenAI Cookbook: [LLM Basics](https://cookbook.openai.com)
  - Video: "How do Large Language Models work?" by StatQuest (15 min YouTube)
- **Hands-On**:
  - Write a prompt and test it in ChatGPT to understand temperature settings
  - Count tokens in a sample prompt using the [tokenizer tool](https://platform.openai.com/tokenizer)

#### 2. Embeddings & Vector Search (2 hours)
- **What to Learn**:
  - What are embeddings (vector representations of text)
  - Why embeddings matter (semantic similarity)
  - Embedding models (text-embedding-3-small vs text-embedding-3-large)
  - Vector similarity (cosine distance, Euclidean distance)
  - Vector databases and approximate nearest neighbor search
- **Resources**:
  - Microsoft Learn: [Understand embeddings](https://learn.microsoft.com/en-us/training/modules/understand-embeddings/) (45 min)
  - OpenAI: [Embeddings Guide](https://platform.openai.com/docs/guides/embeddings)
  - Blog: [Vectors in Search](https://www.algolia.com/blog/ai/what-is-vector-search/)
- **Hands-On**:
  - Generate embeddings for 3-5 sample sentences using OpenAI API
  - Verify why similar sentences have close vector values

#### 3. Prompt Engineering Basics (2 hours)
- **What to Learn**:
  - System prompts (how to instruct LLMs)
  - Few-shot prompting (show examples to guide behavior)
  - Chain-of-thought prompting (make AI think step-by-step)
  - Prompt optimization patterns
  - Common pitfalls (vague instructions, hallucinations)
- **Resources**:
  - OpenAI: [Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
  - Microsoft Learn: [Prompt Engineering](https://learn.microsoft.com/en-us/training/modules/prompt-engineering/) (1 hour)
- **Hands-On**:
  - Write 3 different prompts (vague, specific, few-shot) and compare results
  - Test chain-of-thought: "Think step by step..." vs direct question

#### 4. RAG (Retrieval Augmented Generation) Concept (2 hours)
- **What to Learn**:
  - What is RAG and why it matters (reduce hallucinations, add custom data)
  - RAG workflow: Document → Chunk → Embed → Index → Retrieve → Generate
  - Advantage over fine-tuning (faster, cheaper, updatable)
  - Vector search for retrieval
  - Augmentation (combining retrieved context with prompt)
- **Resources**:
  - Microsoft Learn: [RAG Concepts](https://learn.microsoft.com/en-us/training/modules/rag-concepts/) (1 hour)
  - Blog: [What is RAG?](https://blogs.nvidia.com/blog/what-is-retrieval-augmented-generation-and-why-is-it-important-for-large-language-models/)
- **Hands-On**:
  - Sketch the RAG flow on paper (input → output)
  - Think through: How would you build Document QA using RAG?

---

### 🛠️ Azure Setup (7 hours)

#### Task 1: Create Azure Account & Resources (3 hours)
1. Create Azure account at [portal.azure.com](https://portal.azure.com)
2. Create resource group (e.g., "GenAI-Study")
3. Deploy **Azure OpenAI Service**:
   - Model: GPT-4 (32K or turbo)
   - Model: text-embedding-3-small
   - Note API keys and endpoints
4. Deploy **Azure AI Search**:
   - Tier: Standard (free tier available for testing)
   - Enable Semantic Ranker
5. Save all connection strings and API keys in a secure file (NEVER commit to Git)

- **Resources**:
  - [Create Azure OpenAI Resource](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource)
  - [Deploy Azure AI Search](https://learn.microsoft.com/en-us/azure/search/search-create-service-portal)

#### Task 2: Test Azure OpenAI via REST API (2 hours)
1. Open Postman (or VS Code REST client)
2. Create POST request to Azure OpenAI endpoint:
   ```
   POST https://{your-resource}.openai.azure.com/openai/deployments/{deployment-name}/chat/completions?api-version=2024-02-15-preview

   Headers:
     api-key: {your-api-key}
     Content-Type: application/json

   Body:
   {
     "messages": [{"role": "user", "content": "Hello, who are you?"}],
     "temperature": 0.7,
     "max_tokens": 100
   }
   ```
3. Send request and inspect response
4. Try 3-5 different prompts

- **Resources**: [Azure OpenAI REST API Docs](https://learn.microsoft.com/en-us/azure/ai-services/openai/reference)

#### Task 3: Test Azure AI Search Vector Capabilities (2 hours)
1. Go to Azure AI Search in portal
2. Create a test index with vector field
3. Understand index schema (fields, types, vectors)
4. Read about vector search algorithms (HNSW, DiskANN)
5. Plan your vector index structure for documents

- **Resources**:
  - [Azure AI Search Vector Search Overview](https://learn.microsoft.com/en-us/azure/search/vector-search-overview)
  - [Create Vector Index](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-create-index)

### ✅ Week 1-2 Checkpoint
- Can explain LLMs, embeddings, and RAG
- Can count tokens and understand prompt structure
- Azure resources created and accessible
- Can call Azure OpenAI API successfully
- Understand vector search basics

**Deliverable**: Document with Azure setup (resource names, endpoints, how to test)

---

## Week 3-4: Semantic Kernel & Custom Plugins (20 hours)

### 📖 Learning Topics (12 hours)

#### 1. Semantic Kernel Fundamentals (5 hours)
- **What to Learn**:
  - What is Semantic Kernel (Microsoft's SDK for LLM apps)
  - Core concepts: Kernel, Services, Plugins, Functions
  - Native functions vs. Semantic functions
  - How to initialize Kernel with Azure OpenAI
  - Memory management (short-term, long-term)
  - Request options (temperature, max_tokens, etc.)
- **Resources**:
  - Microsoft Learn: [Getting started with Semantic Kernel](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-get-started/) (1.5 hours)
  - [Semantic Kernel Quick Start](https://learn.microsoft.com/en-us/semantic-kernel/get-started/quick-start-guide)
  - [Semantic Kernel .NET Samples](https://github.com/microsoft/semantic-kernel/tree/main/dotnet/samples)
- **Key Code Pattern**:
  ```csharp
  var builder = Kernel.CreateBuilder();
  builder.AddAzureOpenAIChatCompletion(
      deploymentName: "gpt-4",
      endpoint: "https://your-resource.openai.azure.com",
      apiKey: "your-api-key");
  var kernel = builder.Build();

  var response = await kernel.InvokePromptAsync("Explain RAG in one sentence");
  ```
- **Hands-On**:
  - Create a .NET console app with Semantic Kernel
  - Initialize kernel with Azure OpenAI
  - Send 5 different prompts and see responses

#### 2. Plugins & Function Calling (5 hours)
- **What to Learn**:
  - What are plugins (collections of functions)
  - Native functions (C# methods with `[KernelFunction]` decorator)
  - Semantic functions (prompts stored as templates)
  - Automatic function calling by LLM
  - Function parameters and descriptions
  - Error handling for function calls
- **Resources**:
  - Microsoft Learn: [Creating plugins with Semantic Kernel](https://learn.microsoft.com/en-us/training/modules/semantic-kernel-plugins/) (1.5 hours)
  - [Plugin Samples](https://learn.microsoft.com/en-us/semantic-kernel/concepts/plugins/)
- **Key Code Pattern**:
  ```csharp
  public class MathPlugin
  {
      [KernelFunction("Add")]
      [Description("Adds two numbers")]
      public int Add(int a, int b) => a + b;
  }

  kernel.ImportPluginFromType<MathPlugin>("math");
  ```
- **Hands-On**:
  - Create 2-3 native functions (calculator, API call, data fetch)
  - Test LLM auto-calling your functions
  - Add descriptions so LLM understands what they do

#### 3. Memory & Conversation Context (2 hours)
- **What to Learn**:
  - ChatHistory (maintaining conversation context)
  - Semantic memories (storing and retrieving facts)
  - Context management
  - When to use memory vs. RAG
- **Resources**: [Semantic Kernel Memory](https://learn.microsoft.com/en-us/semantic-kernel/concepts/memory/)
- **Hands-On**: Build a multi-turn conversation that remembers previous responses

---

### 🛠️ Hands-On Projects (8 hours)

#### Project 1: Simple Chatbot with Plugins (4 hours)
- **What to Build**: ASP.NET console or minimal API that:
  - Accepts user input
  - Responds using Semantic Kernel + Azure OpenAI
  - Has at least 2 custom plugins (calculator, weather/API)
  - Maintains conversation history
- **Steps**:
  1. Create Console App (.NET 8+)
  2. Install NuGet packages:
     ```
     dotnet add package Microsoft.SemanticKernel
     dotnet add package Microsoft.Extensions.Logging
     ```
  3. Initialize Kernel with Azure OpenAI
  4. Create `MathPlugin` with `Add()`, `Subtract()`, `Multiply()` functions
  5. Create `WeatherPlugin` returning mock weather (or call real API)
  6. Test: "What is 5 + 3?" → Should call MathPlugin
  7. Test: "What's the weather in NYC?" → Should call WeatherPlugin
- **Verification**:
  - Chatbot runs without errors
  - Custom plugins called correctly
  - Responses make sense

#### Project 2: Deploy Chatbot to Azure Functions (4 hours)
- **What to Build**: Wrap chatbot from Project 1 in an Azure Function (HTTP trigger), deploy with Application Insights logging.
- **Steps**:
  1. Create new Azure Functions project (.NET)
  2. Copy chatbot logic into Function handler
  3. Create HTTP trigger:
     ```csharp
     [Function("Chat")]
     public async Task<HttpResponseData> Chat(
         [HttpTrigger(AuthorizationLevel.Anonymous, "post", Route = null)] HttpRequestData req)
     {
         // Call chatbot logic
         // Return response
     }
     ```
  4. Add Application Insights logging
  5. Deploy via Azure DevOps or `func azure functionapp publish`
  6. Test via curl or Postman
- **Resources**:
  - [Azure Functions Quickstart (.NET)](https://learn.microsoft.com/en-us/azure/azure-functions/functions-get-started)
  - [Add Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)
- **Verification**:
  - Function deployed to Azure
  - Can POST to function URL and get response
  - Logs appear in Application Insights

### ✅ Week 3-4 Checkpoint
- Understand Semantic Kernel core concepts
- Created and registered native plugins
- Built chatbot with automatic function calling
- Deployed to Azure Functions with logging

**Deliverable**: GitHub repo with chatbot code + Azure Functions deployment guide

---

### 🎯 MONTH 1 MILESTONE
**You've built**: A production-ready chatbot with custom plugins deployed on Azure Functions

**Skills Acquired**:
- Understand LLMs, embeddings, RAG concepts
- Use Semantic Kernel to orchestrate LLM calls
- Create native C# plugins
- Deploy to Azure cloud
- Monitor with Application Insights

---

# 🟢 MONTH 2: RAG Pipeline & Vector Databases (Weeks 5-8)

## Week 5-6: Document Processing & Embeddings (20 hours)

### 📖 Learning Topics (8 hours)

#### 1. Azure Document Intelligence (3 hours)
- **What to Learn**:
  - Document processing (OCR, text extraction, layout analysis)
  - Document Intelligence pre-built models (Layout, Read, Invoice, Receipt, etc.)
  - Custom models for your documents
  - Field extraction and document classification
  - Why it matters for RAG (clean data = better retrieval)
- **Resources**:
  - Microsoft Learn: [Process images with Azure Document Intelligence](https://learn.microsoft.com/en-us/training/modules/process-images-with-azure-document-intelligence/) (1.5 hours)
  - [Document Intelligence Overview](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/overview)
- **Hands-On**:
  - Upload a PDF to Document Intelligence REST API via Postman
  - See extracted text and layout

#### 2. Text Chunking Strategies (3 hours)
- **What to Learn**:
  - Why chunking matters (embeddings have token limits)
  - Chunking strategies: fixed size, semantic, recursive
  - Chunk size tuning (smaller = precise, larger = context-aware)
  - Overlapping chunks (preserve context between chunks)
  - Metadata preservation (document name, page number, etc.)
  - Token counting for chunking decisions
- **Key Patterns**:
  - 512 token chunks: Good for semantic search (fine-grained)
  - 1024 token chunks: Balance precision and context
  - Overlaps: 50-100 tokens between chunks to preserve context
- **Hands-On**:
  - Manually chunk a 5-page PDF into pieces
  - Count tokens in each chunk
  - Identify optimal chunk size

#### 3. Embeddings & Similarity (2 hours)
- **What to Learn**:
  - How embeddings are generated (deep learning models)
  - text-embedding-3-small vs text-embedding-3-large (cost/quality tradeoff)
  - Batch embedding (cost-efficient for large datasets)
  - Caching embeddings to reduce API calls
  - Evaluating embedding quality
- **Resources**: [Azure OpenAI Embeddings API](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/understand-embeddings)
- **Hands-On**:
  - Generate embeddings for 20 document chunks
  - Save to file
  - Verify similar documents have close vectors

---

### 🛠️ Hands-On Projects (12 hours)

#### Project 1: Document Ingestion Pipeline (6 hours)
- **What to Build**: C# console app that reads PDFs, extracts text via Document Intelligence, chunks text, generates embeddings, and saves to JSON/CSV.
- **Steps**:
  1. Create Console App
  2. Install packages:
     ```
     dotnet add package Azure.AI.DocumentIntelligence
     dotnet add package Azure.AI.OpenAI
     dotnet add package iTextSharp
     ```
  3. PDF reader:
     ```csharp
     var client = new DocumentIntelligenceClient(...);
     var result = await client.AnalyzeDocumentAsync(uri);
     var text = result.Value.Content;
     ```
  4. Text chunker:
     ```csharp
     public class TextChunker
     {
         public List<Chunk> Chunk(string text, int chunkSize = 512)
         {
             // Split into chunks with overlap
         }
     }
     ```
  5. Generate embeddings:
     ```csharp
     var embeddingClient = new OpenAIClient(...);
     var embeddings = await embeddingClient.GetEmbeddingsAsync(
         new EmbeddingsOptions("text-embedding-3-small", chunks));
     ```
  6. Save results to JSON with metadata
- **Verification**:
  - Process 5 sample PDFs successfully
  - Verify chunks correctly sized
  - Embeddings are 1536-dimensional vectors

#### Project 2: Embeddings Cache & Storage (6 hours)
- **What to Build**: Extend Project 1 to cache embeddings, store metadata, batch embed, and detect duplicates via file hashes.
- **Steps**:
  1. Create cache:
     ```csharp
     public class EmbeddingCache
     {
         private Dictionary<string, float[]> _cache;

         public bool TryGetEmbedding(string text, out float[] embedding) { /* ... */ }
         public void SaveEmbedding(string text, float[] embedding) { /* ... */ }
     }
     ```
  2. Batch embeddings (single API call per group)
  3. Store metadata (source doc, page number)
  4. Persist cache to disk
- **Verification**:
  - Second run faster (cache hits)
  - Metadata preserved
  - Can reload cache from disk

### ✅ Week 5-6 Checkpoint
- Extract text from PDFs via Document Intelligence
- Implemented text chunking with optimal size
- Generate embeddings for chunks
- Built caching to reduce API costs

**Deliverable**: GitHub repo with document pipeline + sample embeddings data file

---

## Week 7-8: Vector Search & RAG Integration (20 hours)

### 📖 Learning Topics (10 hours)

#### 1. Vector Store Abstractions & Azure AI Search (4 hours)
- **What to Learn**:
  - `Microsoft.Extensions.VectorData` abstractions
  - Vector indexing algorithms (HNSW, DiskANN, flat)
  - Creating vector collections in Azure AI Search
  - Metadata filtering in vector search
  - Hybrid search (vector + keyword)
  - Search ranking and scoring
- **Resources**:
  - Microsoft Learn: [Vector Store Connectors in Semantic Kernel](https://learn.microsoft.com/en-us/semantic-kernel/concepts/vector-store-connectors/)
  - [Azure AI Search Vector How-To](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-create-index)
  - [Semantic Ranker](https://learn.microsoft.com/en-us/azure/search/semantic-search-overview)
- **Hands-On**:
  - Create vector index in Azure AI Search (Portal or REST)
  - Test search via REST API

#### 2. Building RAG Retrieval Pipeline (4 hours)
- **What to Learn**:
  - Retrieval flow: user query → embed → search → retrieve
  - Ranking strategies (relevance, recency, custom scoring)
  - Handling retrieval edge cases (no results, low confidence)
  - Reranking
  - Latency optimization (parallel retrieval, caching)
- **Resources**: [RAG Advanced Concepts](https://learn.microsoft.com/en-us/training/modules/rag-advanced-concepts/)
- **Key Patterns**:
  - Multi-query: Ask LLM to generate 3 variations of query, retrieve for each
  - Re-ranking: Use LLM or ML model to rank initial results
  - Hybrid: Combine vector + keyword search
- **Hands-On**:
  - Manually test retrieval: embed a query, search vector DB, see results
  - Evaluate relevance of top-5 results

#### 3. Augmenting Prompts with Retrieved Context (2 hours)
- **What to Learn**:
  - RAG augmentation pattern (retrieved docs + user query + system prompt)
  - Formatting context for LLM
  - Citation tracking
  - Handling contradictory information
  - Confidence scoring
- **Key Pattern**:
  ```
  System: You are a helpful assistant. Answer using the provided context.

  Context:
  [Top 3 retrieved documents here]

  User Question:
  [Original user query]

  Assistant: [Answer based on context, with citations]
  ```
- **Hands-On**:
  - Manually create augmented prompt
  - Send to LLM, see answer with citations

---

### 🛠️ Hands-On Projects (10 hours)

#### Project 1: Vector Index Setup & Indexing (4 hours)
- **What to Build**: C# console app that creates a vector index in Azure AI Search, uploads embeddings with metadata, and tests sample queries.
- **Steps**:
  1. Create console app
  2. Install: `dotnet add package Azure.Search.Documents`
  3. Create index schema:
     ```csharp
     var index = new SearchIndex("documents")
     {
         Fields = new FieldCollection
         {
             new SearchField("id", SearchFieldDataType.String) { IsKey = true },
             new SearchField("title", SearchFieldDataType.String),
             new SearchField("content", SearchFieldDataType.String),
             new SearchField("vector", SearchFieldDataType.Collection(SearchFieldDataType.Single))
             {
                 IsSearchable = true,
                 VectorSearchDimensions = 1536,
                 VectorSearchProfile = "myProfile"
             }
         }
     };
     ```
  4. Upload documents:
     ```csharp
     var documents = new List<Document>
     {
         new Document { id = "1", title = "...", content = "...", vector = embedding }
     };
     await searchClient.UploadDocumentsAsync(documents);
     ```
  5. Test search query
- **Verification**:
  - Index created in Azure AI Search
  - Documents uploaded with embeddings
  - Vector search returns results

#### Project 2: Full RAG Query Pipeline (6 hours)
- **What to Build**: Complete RAG: accept user query, embed, retrieve top-k, augment, call GPT-4 via Semantic Kernel, return answer with citations.
- **Steps**:
  1. Create RAG class:
     ```csharp
     public class RAGPipeline
     {
         private IVectorStoreRecordCollection<string, Document> _vectorStore;
         private ITextGenerationService _textGen;

         public async Task<Answer> QueryAsync(string userQuery)
         {
             var queryEmbedding = await EmbedQueryAsync(userQuery);
             var results = await _vectorStore.GetNearestMatchesAsync(queryEmbedding);
             var augmentedPrompt = BuildAugmentedPrompt(userQuery, results);
             var answer = await _textGen.GenerateAsync(augmentedPrompt);
             return new Answer { Text = answer, Sources = results };
         }
     }
     ```
  2. Integrate Semantic Kernel for LLM calls
  3. Handle edge cases (empty results, low confidence)
  4. Format response with citations
- **Verification**:
  - Ask 5-10 questions on indexed documents
  - Answers accurate with citations
  - Response time <3 seconds

### ✅ Week 7-8 Checkpoint
- Vector index created and populated
- Can search vectors and retrieve relevant documents
- Built complete RAG pipeline (query → retrieve → augment → answer)
- Answers include source citations

**Deliverable**: GitHub repo with RAG pipeline + test queries + evaluation metrics

---

### 🎯 MONTH 2 MILESTONE
**You've built**: End-to-end RAG system that answers questions on indexed documents

**Skills Acquired**:
- Document processing and text extraction
- Text chunking and optimization
- Embedding generation and caching
- Vector indexing and search
- RAG pipeline orchestration with Semantic Kernel
- Prompt augmentation and citation tracking

---

# 🟣 MONTH 3: Production App & Deployment (Weeks 9-12)

## Week 9-10: Full-Stack Document QA Application (20 hours)

### 📖 Architecture & API Design (3 hours)

**REST API Endpoints**:
```
POST   /api/documents/upload    Upload PDF; returns document ID, indexing status
GET    /api/documents           List all indexed documents
DELETE /api/documents/{id}      Remove document from index
POST   /api/query               Ask question; returns answer + sources + confidence
GET    /api/health              Health check
```

- **Resources**:
  - [RESTful API Design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)
  - [Swagger/OpenAPI in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger)

---

### 🛠️ Full-Stack Application Development (17 hours)

#### Part 1: ASP.NET Core API Backend (10 hours)

**Project Structure**:
```
DocumentQA.API/
├── Controllers/
│   ├── DocumentsController.cs
│   └── QueryController.cs
├── Services/
│   ├── DocumentIngestService.cs
│   ├── RAGService.cs
│   └── EmbeddingService.cs
├── Models/
│   ├── UploadRequest.cs
│   ├── QueryRequest.cs
│   ├── QueryResponse.cs
│   └── Document.cs
├── Program.cs
└── appsettings.json
```

**Step 1 — Project Setup (1 hour)**:
```bash
dotnet new webapi -n DocumentQA.API
cd DocumentQA.API
dotnet add package Microsoft.SemanticKernel
dotnet add package Azure.Search.Documents
dotnet add package Azure.AI.DocumentIntelligence
dotnet add package Azure.AI.OpenAI
```

**Step 2 — Configure Dependency Injection (2 hours)**:
```csharp
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddScoped<IEmbeddingService, EmbeddingService>();
builder.Services.AddScoped<IRAGService, RAGService>();
builder.Services.AddScoped<IDocumentService, DocumentService>();

builder.Services.AddSingleton(new SearchClient(
    new Uri(builder.Configuration["AzureSearch:Endpoint"]),
    new AzureKeyCredential(builder.Configuration["AzureSearch:ApiKey"])));

var kernel = Kernel.CreateBuilder()
    .AddAzureOpenAIChatCompletion(/* ... */)
    .Build();
builder.Services.AddSingleton(kernel);
```

**Step 3 — Documents Controller (3 hours)**:
```csharp
[ApiController]
[Route("api/[controller]")]
public class DocumentsController : ControllerBase
{
    private readonly IDocumentService _docService;

    [HttpPost("upload")]
    public async Task<IActionResult> Upload(IFormFile file)
    {
        // Validate file (PDF)
        // Call Document Intelligence
        // Chunk text
        // Generate embeddings
        // Index in Azure Search
        return Ok(new { documentId = "...", status = "indexed" });
    }

    [HttpGet]
    public async Task<IActionResult> GetDocuments() => Ok(await _docService.ListAsync());

    [HttpDelete("{id}")]
    public async Task<IActionResult> DeleteDocument(string id) { /* ... */ return Ok(); }
}
```

**Step 4 — Query Controller (3 hours)**:
```csharp
[ApiController]
[Route("api/[controller]")]
public class QueryController : ControllerBase
{
    private readonly IRAGService _ragService;

    [HttpPost]
    public async Task<IActionResult> Query([FromBody] QueryRequest request)
    {
        var result = await _ragService.QueryAsync(request.Question, request.TopK);
        return Ok(new QueryResponse
        {
            Answer = result.Answer,
            Sources = result.Sources,
            Confidence = result.Confidence
        });
    }
}
```

**Step 5 — Error Handling & Logging (1 hour)**:
```csharp
app.UseExceptionHandler(errorApp =>
{
    errorApp.Run(async context =>
    {
        var exception = context.Features.Get<IExceptionHandlerFeature>();
        _logger.LogError(exception.Error, "Unhandled exception");
        context.Response.StatusCode = 500;
        await context.Response.WriteAsJsonAsync(new { error = "An error occurred" });
    });
});
```

- **Resources**:
  - [ASP.NET Core API Best Practices](https://learn.microsoft.com/en-us/aspnet/core/web-api/)
  - [Error Handling](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/error-handling)

---

#### Part 2: Frontend (Optional, 7 hours)

**Option A — Skip Frontend (Recommended if short on time)**:
- Focus on robust API
- Test via Postman/curl
- Use Swagger UI for demo

**Option B — Simple React UI**:
- Components: Document Upload (drag-drop), Document List, Query Input & Results, Source Citations
- Stack: React 18+, Axios, Tailwind CSS
- Steps:
  1. `npx create-react-app documentqa-ui`
  2. Create `UploadForm.tsx`, `DocumentList.tsx`, `QueryPanel.tsx`
  3. Implement API calls
  4. Add error handling and loading states
  5. Display results with source links
  6. Style with Tailwind
- Example:
  ```tsx
  export function QueryPanel() {
      const [question, setQuestion] = useState("");
      const [result, setResult] = useState(null);

      async function handleQuery() {
          const res = await fetch("/api/query", {
              method: "POST",
              body: JSON.stringify({ question, topK: 5 })
          });
          setResult(await res.json());
      }

      return (
          <div>
              <input value={question} onChange={(e) => setQuestion(e.target.value)} />
              <button onClick={handleQuery}>Ask</button>
              {result && <div>{result.answer}</div>}
          </div>
      );
  }
  ```

### ✅ Week 9-10 Checkpoint
- REST API fully functional (all endpoints working)
- Can upload documents and ask questions via API
- Response includes citations and confidence
- Robust error handling
- (Optional) React frontend displays results

**Deliverable**: GitHub repo with backend + (optional) frontend + Swagger docs

---

## Week 11: Evaluation, Monitoring & Optimization (10 hours)

### 📊 Evaluation & Quality Metrics (5 hours)

#### 1. Retrieval Quality Metrics (3 hours)
- **Metrics**:
  - **Relevance Score**: Does retrieved document answer the question? (1-5)
  - **Latency**: Query response time (<2 sec target)
  - **Coverage**: % of documents retrieved per query
  - **Ranking Quality**: Are top results more relevant?
- **Steps**:
  1. Create test dataset (questions + expected answers)
  2. Run queries and collect results
  3. Manually evaluate 10 queries
  4. Use GPT-4 to auto-evaluate remaining 20
  5. Log metrics to Application Insights
- **Example**:
  ```csharp
  public async Task<EvaluationResult> EvaluateQueryAsync(string question, string answer)
  {
      var evaluationPrompt = $@"
      Question: {question}
      Answer: {answer}

      Rate relevance (1-5), groundedness (1-5), and if answer is complete (yes/no).
      Return JSON.";

      var evaluation = await _kernel.InvokePromptAsync(evaluationPrompt);
      return JsonSerializer.Deserialize<EvaluationResult>(evaluation);
  }
  ```

#### 2. Answer Quality Evaluation (2 hours)
- **Metrics**: Groundedness, Hallucination Rate, Citation Accuracy
- **Implementation**:
  - 50 test queries
  - Manually evaluate 10
  - Calculate hallucination rate
  - Report findings

### 📈 Monitoring & Observability (5 hours)

#### 1. Application Insights Setup (2 hours)
- **Log**: API request/response times, vector search latency, LLM call latency, error rates, cost per query
- **Code**:
  ```csharp
  services.AddApplicationInsightsTelemetry(
      builder.Configuration["APPLICATIONINSIGHTS_CONNECTION_STRING"]);

  _telemetryClient.TrackEvent("QueryExecuted",
      new Dictionary<string, string>
      {
          { "question_length", question.Length.ToString() },
          { "retrieved_documents", topK.ToString() }
      },
      new Dictionary<string, double>
      {
          { "latency_ms", stopwatch.ElapsedMilliseconds },
          { "confidence", result.Confidence }
      });
  ```
- **Resources**: [Application Insights with .NET](https://learn.microsoft.com/en-us/azure/azure-monitor/app/asp-net-core)

#### 2. Performance Optimization (3 hours)
- **Analyze**: Profile slow endpoints, vector search latency, embedding generation, cache hit rates
- **Strategies**:
  - **Query Parallelization**: Search in parallel
  - **Caching**: LRU cache for frequent queries
  - **Chunking Tuning**: Larger chunks = fewer searches but less precision
  - **Embedding Batching**: Background batch jobs
- **Example**:
  ```csharp
  public class RAGServiceWithCache : IRAGService
  {
      private readonly IMemoryCache _cache;

      public async Task<QueryResult> QueryAsync(string question)
      {
          var cacheKey = $"query:{question.GetHashCode()}";
          if (_cache.TryGetValue(cacheKey, out QueryResult cached)) return cached;

          var result = await FullRAGPipeline(question);
          _cache.Set(cacheKey, result, TimeSpan.FromHours(1));
          return result;
      }
  }
  ```

### ✅ Week 11 Checkpoint
- Evaluation metrics show >80% relevance
- Response latency <2 seconds
- Application Insights dashboard configured
- Optimization opportunities identified

**Deliverable**: Evaluation report + metrics dashboard + optimization recommendations

---

## Week 12: Deployment & Production Readiness (10 hours)

### 🐳 Containerization (3 hours)

**Dockerfile**:
```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS builder
WORKDIR /build
COPY . .
RUN dotnet publish -c Release -o /app

FROM runtime
COPY --from=builder /app .
ENTRYPOINT ["dotnet", "DocumentQA.API.dll"]
```

**docker-compose.yml** (local testing):
```yaml
version: '3.8'
services:
  api:
    build: .
    ports:
      - "5000:80"
    environment:
      - AzureOpenAI__Endpoint=${AZURE_OPENAI_ENDPOINT}
      - AzureOpenAI__ApiKey=${AZURE_OPENAI_KEY}
```

**Steps**:
1. Create `Dockerfile`
2. Build: `docker build -t documentqa:latest .`
3. Test locally: `docker run -p 5000:80 documentqa:latest`
4. Verify API works in container

### ☁️ Azure Container Apps Deployment (4 hours)
```bash
# Create container registry
az acr create -g GenAI-Study -n documentqaregistry --sku Basic

# Build and push image
az acr build --registry documentqaregistry --image documentqa:latest .

# Create Container Apps environment
az containerapp env create -n documentqa-env -g GenAI-Study

# Deploy container app
az containerapp create \
  -n documentqa-api \
  -g GenAI-Study \
  --image documentqaregistry.azurecr.io/documentqa:latest \
  --environment documentqa-env \
  --ingress external \
  --target-port 80 \
  --env-vars AZURE_OPENAI_ENDPOINT=${ENDPOINT} AZURE_OPENAI_KEY=${KEY}
```

**Auto-scaling**:
```bash
az containerapp update \
  -n documentqa-api \
  -g GenAI-Study \
  --scale-rule-name http-rule \
  --scale-rule-type http \
  --scale-rule-http-concurrency 50
```

- **Resources**: [Deploy to Container Apps](https://learn.microsoft.com/en-us/azure/container-apps/quickstart-portal)

### 🔄 CI/CD Pipeline (2 hours)

**Azure DevOps Pipeline (azure-pipelines.yml)**:
```yaml
trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

stages:
  - stage: Build
    jobs:
      - job: BuildAndTest
        steps:
          - task: UseDotNet@2
            inputs:
              version: '8.0.x'
          - task: DotNetCoreCLI@2
            inputs:
              command: 'build'
              arguments: '--configuration Release'
          - task: DotNetCoreCLI@2
            inputs:
              command: 'test'
              arguments: '--configuration Release'

  - stage: Deploy
    dependsOn: Build
    condition: succeeded()
    jobs:
      - deployment: DeployToAzure
        environment: production
        strategy:
          runOnce:
            deploy:
              steps:
                - task: AzureCLI@2
                  inputs:
                    azureSubscription: 'Azure Subscription'
                    scriptType: 'bash'
                    scriptLocation: 'inlineScript'
                    inlineScript: |
                      az acr build --registry documentqaregistry --image documentqa:$(Build.BuildId) .
                      az containerapp update -n documentqa-api -g GenAI-Study --image documentqaregistry.azurecr.io/documentqa:$(Build.BuildId)
```

- **Resources**: [Azure DevOps Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/)

### 🔐 Security & Best Practices (1 hour)

**Auth**:
- Use Azure Managed Identity (no hardcoded keys)
- Implement API key or OAuth2 for clients
- Rate limiting
```csharp
var credential = new DefaultAzureCredential();
var searchClient = new SearchClient(endpoint, credential);
```

**Cost Optimization**:
- Monitor Azure OpenAI spend daily
- Cache embeddings
- Use batch APIs
- Set budget alerts

**Documentation**: Swagger, deployment runbook, architecture diagram, cost estimation

**Testing**: Unit tests, integration tests, load testing (100 concurrent requests)

### ✅ Week 12 Checkpoint
- Application containerized
- Deployed to Azure Container Apps
- CI/CD pipeline automated
- Auto-scaling configured
- Monitoring and logging active
- Security best practices implemented
- Documentation complete

**Deliverable**: Deployment runbook + Docker image + CI/CD pipeline + monitoring dashboard

---

### 🎯 MONTH 3 MILESTONE
**You've built**: Production-ready GenAI application deployed to Azure

**Final app includes**: REST API, RAG pipeline, evaluation metrics, monitoring, CI/CD, security, auto-scaling, cost optimization

---

# ✨ 3-Month Bootcamp Summary

**Total Time**: 120-180 hours (10-15 hrs/week)

## Projects Completed
1. **Month 1**: Semantic Kernel chatbot deployed to Azure Functions
2. **Month 2**: RAG pipeline processing documents and generating answers
3. **Month 3**: Production Document QA application deployed to Container Apps

## Technologies Mastered
| Technology | Proficiency Level |
|---|---|
| Semantic Kernel | Intermediate (plugins, orchestration) |
| Azure OpenAI | Intermediate (chat, embeddings) |
| Azure AI Search | Intermediate (indexing, retrieval) |
| Document Intelligence | Beginner-Intermediate |
| ASP.NET Core | Advanced |
| Docker & Container Apps | Intermediate |
| Azure DevOps | Intermediate (CI/CD) |

## Portfolio Assets
- GitHub repo with production code
- Deployment documentation & runbook
- API documentation (Swagger)
- Monitoring dashboard
- Demo video

## Interview Preparation
- Explain RAG architecture (retrieval + augmentation + generation)
- Discuss Semantic Kernel design patterns
- Talk about vector search algorithms (HNSW, DiskANN)
- Justify tech decisions (Azure AI Search vs Cosmos DB, etc.)
- Demo production application running on Azure

## Next Steps (Month 4+)
- Multi-agent systems
- Fine-tuning embeddings on domain-specific data
- Advanced evaluation (groundedness, hallucination scoring)
- Scaling (1000s of documents, concurrent users)
- Voice interface (Whisper + TTS)
- Multi-modal support (images in PDFs)

---

# 📌 Key Resources

## Learning
- [Microsoft Learn: Develop Generative AI Apps in Azure](https://learn.microsoft.com/en-us/training/paths/develop-generative-ai-apps/)
- [Semantic Kernel Documentation](https://learn.microsoft.com/en-us/semantic-kernel/)
- [Azure OpenAI Service](https://learn.microsoft.com/en-us/azure/ai-services/openai/)

## Tools & SDKs
- [Semantic Kernel GitHub](https://github.com/microsoft/semantic-kernel)
- [Azure SDK for .NET](https://github.com/Azure/azure-sdk-for-net)
- [Semantic Kernel Discord](https://aka.ms/SKDiscord)

## Sample Projects
- [Azure Samples](https://github.com/Azure-Samples)
- [Contoso Chat (full RAG reference)](https://github.com/Azure-Samples/contoso-chat)
