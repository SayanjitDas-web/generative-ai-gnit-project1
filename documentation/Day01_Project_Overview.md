# 🎓 Day 1: Project Overview & GenAI Stack

Welcome to the **Generative AI Portfolio Cohort**! 🚀

In this 10-day journey, we are going to build a sophisticated AI-powered system that takes a raw PDF resume and transforms it into a beautiful, interactive personal website.

## 🌟 The Vision
We aren't just calling an API; we are building a **Stateful AI Workflow**. Imagine an intelligent assistant that:
1. **Reads** your PDF.
2. **Understands** your skills and experience.
3. **Writes** creative marketing copy for your website.
4. **Responds** to visitor questions as your "Digital Representative."

## 🛠️ The Generative AI Stack
To achieve this, we use a cutting-edge stack of tools:

### 1. 🧠 LLM Provider: OpenRouter (GPT-3.5 Turbo)
We use **OpenRouter** as our gateway to powerful models. It allows us to swap models easily and provides a standardized API for any LLM (OpenAI, Anthropic, Google, etc.).

### 2. 🔗 Orchestration: LangChain
LangChain is the "duct tape" of the AI world. It helps us manage prompts, interact with LLMs, and handle data structures like "Messages" (System, Human, AI).

### 3. 🕸️ Brain of the System: LangGraph
Unlike simple "chains," **LangGraph** allows us to create complex workflows with loops, logic, and state management. It treats our AI process as a "Graph" where data flows between nodes.

### 4. 🗄️ Memory: ChromaDB (Vector Database)
Generative AI can "forget" things if the input is too long. We use **ChromaDB** to store chunks of your resume so that the AI can quickly "look up" relevant info during a live chat. This is called **RAG (Retrieval-Augmented Generation)**.

---

## 📂 Where is the AI Code?
- `generator.py`: Contains the **LangGraph** logic and extraction prompts.
- `database.py`: Handles the **ChromaDB** vector storage.
- `main.py`: Integrates everything into the web server.

> [!TIP]
> **Today's Goal:** Browse through `generator.py` and see if you can spot where we define our "Graph State". Don't worry if it looks complex; we will break it down Day by Day!

---
*Next Up: Day 2 - Mastering LLM Basics (Prompting & OpenRouter)*
