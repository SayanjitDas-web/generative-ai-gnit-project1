# 🎓 Day 8: RAG: Giving the AI a Memory (Part 1 - Indexing)

LLMs have a "Context Window" (like short-term memory). But what if your resume is 20 pages long? Or you have 1,000 users? We use **RAG (Retrieval-Augmented Generation)**.

## 📚 What is RAG?
RAG is like giving the AI a **Library Card**. Instead of memorizing everything, the AI looks up the right book when it needs to answer a question.

## 🔨 Step 1: Text Splitting
In `main.py` (line 103), we split the resume into "Chunks":
```python
chunks = [resume_text[i:i+1000] for i in range(0, len(resume_text), 1000)]
```
Why? Because searching through 100 small pieces is faster and more accurate than searching through 1 giant document.

## 💾 Step 2: Vector Storage (ChromaDB)
In `database.py`, we use **ChromaDB**. It turns text into "Vectors" (numbers).
- **Embeddings:** Numbers that represent the *meaning* of the text.
- **Upsert:** We "upload or update" these numbers into the database.

```python
self.collection.upsert(
    documents=text_chunks,
    metadatas=metadata_list,
    ids=ids
)
```

> [!NOTE]
> **Semantic Search:** Unlike Ctrl+F (which looks for exact words), Vector DBs look for **Meaning**. A search for "Programming" will find "Coding", "Software engineering", and "Python" automatically!

---
*Next Up: Day 9 - RAG: Giving the AI a Memory (Part 2 - Retrieval & Chat)*
