# 🛠️ Project Breakdown: Foundation vs. GenAI

To help you structure your 10-day cohort, here is a guide on which parts of the code are the **Foundation** (non-AI) and which are the **GenAI Extensions**.

## 🏗️ 1. The Foundation (Give these to students first)
These files and sections handle the web server, users, and traditional database logic. Students should understand these before moving to AI.

| File | Non-AI Responsibility |
| :--- | :--- |
| `main.py` | FastAPI setup, Cookie Auth, Database sessions, Template rendering, Landing/Login/Register routes. |
| `models.py` | SQLAlchemy User & Portfolio schemas. (All content in this file is standard DB logic). |
| `auth.py` | JWT Token generation, Password hashing (bcrypt). |
| `database.py` | *Note: This file is purely for AI (ChromaDB), but the `get_db()` function in `auth.py` handles the main SQL database.* |
| `templates/` | All HTML files (Landing, Dashboard, Login, etc.). |
| `static/` | CSS styles and client-side JavaScript. |
| `requirements.txt` | `fastapi`, `uvicorn`, `sqlalchemy`, `bcrypt`, `jinja2`, `python-jose`. |

## 🧠 2. The GenAI Extensions (Add these day-by-day)
These are the parts students will "build" or "unlocked" during your 10-day cohort.

### A. The Core AI Brain (`generator.py`)
- **Everything** in this file is Generative AI.
- **Concepts:** LangChain, LangGraph, State Management, Prompting, JSON Parsing.

### B. The Memory System (`database.py`)
- **Everything** in this file is AI-related.
- **Concepts:** Vector Databases, Embeddings, ChromaDB, RAG Indexing.

### C. The Integration Routes (`main.py`)
Wait to introduce these specific blocks in `main.py` until the relevant cohort day:

1. **PDF Text Extraction (Lines 95-101):** Uses `pypdf` to turn a file into a string.
2. **RAG Indexing (Lines 102-105):** Sending data to ChromaDB.
3. **Portfolio Generation (Lines 107-108):** Calling the LangGraph workflow.
4. **Chat Representative Route (Lines 138-177):** The entire `/chat` POST route is Generative AI + RAG.

## 🚀 Suggested Delivery Plan
- **Day 0:** Give students the "Foundation" package (a working login/register system with a dashboard).
- **Day 1-7:** Gradually implement the logic inside `generator.py` and the `/generate` route.
- **Day 8-10:** Implement `database.py` and the `/chat` representative features.

> [!TIP]
> You can provide `main.py` with the AI routes commented out or "TODO" to give students a clear roadmap of where the AI logic fits into a real web application.
