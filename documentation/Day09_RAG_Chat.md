# 🎓 Day 9: RAG: Giving the AI a Memory (Part 2 - Retrieval & Chat)

Yesterday we stored the data. Today, we **Use** it to create a Chat Assistant.

## 🕵️ The Retrieval Process
When a visitor asks a question (like "Where did he work in 2022?"), we don't send the question to the AI yet. 
First, we ask **ChromaDB**: "Give me the 3 most relevant chunks about 2022." (See `main.py` line 147).

```python
context_chunks = db_vector.query_resume(user_id, query)
context = "\n".join(context_chunks)
```

## 🧠 Augmented Generation
Now we have:
1. The **Visitor's Question**.
2. The **Relevant Resume Chunks** (the "Context").

We combine them in the `sys_prompt` (line 150) and send them to the LLM. Now the LLM can answer accurately because it has the facts right in front of it!

## 🔐 Multi-User Isolation
In `database.py`, notice the `where={"user_id": user_id}` filter. 
**CRITICAL:** Without this, the AI might answer a question about User A using User B's resume! RAG must always be "scoped" by user.

> [!IMPORTANT]
> **The Secret Sauce:** The LLM is NOT answering from memory. It is essentially "Reading the facts" provided in the context and summarizing them for the user.

---
*Next Up: Day 10 - AI Safety & Deployment (System Prompts & Boundaries)*
