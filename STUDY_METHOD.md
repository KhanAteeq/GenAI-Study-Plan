# 🧠 Study Method & Workflow

A short, opinionated guide to how I work through this 12-week plan. Use it as a reminder when motivation dips.

---

## 1. Daily Loop (1-2 hrs)

1. **Open today's week issue** on GitHub.
2. **Pick 1-3 tasks** — no more.
3. **Pomodoro**: 25 min focus → 5 min break. Repeat 2-4 times.
4. **Commit often**:
   ```
   git commit -m "Week 3 Day 2: MathPlugin returns correct result"
   ```
5. **Comment on the issue**: 1-3 lines about what you learned, blockers, links to commits.
6. **Stop on time** — burnout kills 12-week plans.

---

## 2. Weekly Loop (Sunday, 30 min)

1. Tick remaining checkboxes on this week's issue.
2. Write a closing comment:
   - ✅ What got done
   - ❌ What didn't (and why)
   - 🧠 Top 3 learnings
   - 🔜 Plan for next week
3. Close the issue → assign next week's issue to yourself.
4. Update **README.md** progress numbers (or let the GitHub Action do it).
5. (Optional) Post a short LinkedIn/Twitter update.

---

## 3. Monthly Loop (end of Month 1, 2, 3)

1. Verify the milestone deliverable runs end-to-end.
2. Record a 1-2 min demo (Loom / OBS).
3. Add the demo link to the project's README in `code/`.
4. Update root README milestone checkbox.
5. Reflect: keep / change / drop for next month.

---

## 4. Note-Taking Rules

- One file per topic in `notes/`. Filename: `week-XX-topic.md`.
- Always include these sections:
  - **Concept** — plain-English explanation
  - **Why it matters** — link to RAG / GenAI app
  - **Code** — minimal working snippet
  - **Gotchas** — what tripped you up
  - **Resources** — links you used
- **Feynman test**: if you can't write the Concept section in your own words, you don't understand it yet.

---

## 5. Coding Rules

- Always start a project with a `README.md` (what / why / how to run).
- Never commit secrets — they go in `.env` (gitignored) or User Secrets.
- Commit small, often, with messages that name the **week + outcome**.
- Tag working snapshots: `git tag week-04-chatbot-working`.
- Each project folder should have a tiny "Demo" section with screenshot or GIF.

---

## 6. Time-Boxing Rules

| Situation | Action |
|---|---|
| Stuck on a bug >45 min | Stop. Write the question down. Search SK Discord / GitHub issues. |
| Stuck on a concept >2 hrs | Move on. Open a `learning-note` issue. Come back tomorrow. |
| A task takes 2× the estimate | Cut scope, not quality. Document what's left as a follow-up. |
| Behind by a full week | Skip the optional parts (e.g., React UI in Week 10). |

---

## 7. Anti-Patterns to Avoid

- ❌ Reading 5 tutorials before writing any code.
- ❌ Refactoring chatbot code for the 4th time instead of moving to RAG.
- ❌ Trying to learn Python / LangChain / LlamaIndex on the side. Stay in .NET + SK.
- ❌ Skipping the deliverable because "the code already works in my head".
- ❌ Pushing only when "everything is clean". Push messy WIP — that's the diary.

---

## 8. Interview-Readiness Checklist (final review)

- [ ] Can whiteboard the RAG pipeline (5 components, why each exists)
- [ ] Can compare HNSW vs flat vs DiskANN at a high level
- [ ] Can justify Azure AI Search vs Cosmos DB vector vs Qdrant
- [ ] Can demo the Document QA app live (with backup video)
- [ ] Can talk about evaluation (relevance, groundedness, hallucination)
- [ ] Can talk about cost (tokens, embeddings, search units)
- [ ] Can talk about deployment (containers, scaling, CI/CD, observability)

---

## 9. Useful Aliases / Snippets

PowerShell git aliases (add to `$PROFILE`):
```powershell
function gs { git status }
function ga { git add . }
function gc { param($m) git commit -m $m }
function gp { git push }
function week { git commit -am "Week $args" }
```

Daily 30-second standup template (paste into the week's issue):
```
**Date**: 2026-05-XX
**Done**: …
**Blockers**: …
**Next**: …
```
