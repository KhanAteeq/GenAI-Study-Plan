# 🐍 Python-Lite Track (Optional, ~4 hours total)

A **minimal** Python side-track to support your .NET GenAI study. Goal: be able to **read, run, and tweak** Python GenAI samples — not become a Python developer.

> ⚠️ Skip this entirely if you're behind on the main plan. .NET is the primary path.

---

## 🎯 What You'll Learn

| Notebook | Topic | Time |
|---|---|---|
| [01-syntax-basics.ipynb](01-syntax-basics.ipynb) | Python syntax for C# devs | 1 hr |
| [02-openai-api.ipynb](02-openai-api.ipynb) | Call Azure OpenAI from Python | 1 hr |
| [03-langchain-hello-rag.ipynb](03-langchain-hello-rag.ipynb) | Tiny RAG using LangChain | 1 hr |
| [04-huggingface-embeddings.ipynb](04-huggingface-embeddings.ipynb) | Local embeddings with Hugging Face | 1 hr |

Slot these into **Weeks 5-8** of the main plan (Month 2) — they reinforce the same RAG concepts you're learning in .NET.

---

## 🛠️ Setup (one-time, 10 min)

### 1. Install Python 3.11+
Download from [python.org](https://www.python.org/downloads/) — **check "Add Python to PATH"** during install.

Verify:
```powershell
python --version    # should show 3.11.x or 3.12.x
```

### 2. Create a virtual environment
```powershell
cd d:\GenerativeAI\python-side
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

> If activation is blocked: `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`

You'll see `(.venv)` in your prompt — that means you're isolated from system Python.

### 3. Install packages
```powershell
pip install -r requirements.txt
```

### 4. Open in VS Code
```powershell
code .
```

VS Code will detect notebooks. Install the **Python** + **Jupyter** extensions if prompted. Pick the `.venv` interpreter when asked.

### 5. Create a `.env` file (NEVER commit)
```env
AZURE_OPENAI_ENDPOINT=https://your-resource.openai.azure.com
AZURE_OPENAI_KEY=your-key
AZURE_OPENAI_CHAT_DEPLOYMENT=gpt-4
AZURE_OPENAI_EMBED_DEPLOYMENT=text-embedding-3-small
```

Already covered by the root `.gitignore` — safe.

---

## 🧠 C# → Python Cheat Sheet

| C# | Python |
|---|---|
| `var x = 5;` | `x = 5` |
| `string s = "hi";` | `s = "hi"` |
| `List<int> nums = new() {1,2,3};` | `nums = [1, 2, 3]` |
| `Dictionary<string,int>` | `d = {"a": 1}` |
| `if (x > 5) { ... }` | `if x > 5:` (indent matters!) |
| `foreach (var n in nums)` | `for n in nums:` |
| `public int Add(int a, int b) => a+b;` | `def add(a, b): return a + b` |
| `null` | `None` |
| `true` / `false` | `True` / `False` |
| `// comment` | `# comment` |
| `await SomethingAsync()` | `await something()` (in `async def`) |

---

## 🚀 Workflow

1. Open notebook → run cells top-to-bottom (`Shift+Enter`)
2. Tweak values and re-run
3. Commit progress: `git add python-side/ && git commit -m "Python: notebook 01 done"`

That's it. No project structure, no production code — just exploration.
