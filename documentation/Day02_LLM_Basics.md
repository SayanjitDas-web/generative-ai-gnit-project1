# 🎓 Day 2: Mastering LLM Basics (Prompting & OpenRouter)

Today we dive into the heart of Generative AI: **The Large Language Model (LLM)**.

## 🗝️ What is OpenRouter?
In this project, we use **OpenRouter**. It’s like a "Universal Remote" for AI models. Instead of signing up for OpenAI, Anthropic, and Google separately, you use one API key to access them all.

### Why GPT-3.5 Turbo?
We use `gpt-3.5-turbo` because it's:
1. **Fast:** Great for real-time web experiences.
2. **Cheap:** Perfect for learning and testing.
3. **Smart Enough:** It handles JSON formatting very well if prompted correctly.

## 💬 The Anatomy of a Conversation
When we talk to the AI in `generator.py` or `main.py`, we don't just send a string. We send a list of **Messages**:

1. **SystemMessage:** The "Rules". It tells the AI who it is (e.g., "You are an expert resume parser").
2. **HumanMessage:** The "Question". This is the actual data or query (e.g., "Here is my resume, please extract my skills").

### Example from `generator.py`:
```python
response = llm.invoke([
    SystemMessage(content="You are an expert resume parser. Respond ONLY with raw JSON."),
    HumanMessage(content=prompt)
])
```

## 🪄 Prompt Engineering Secrets
Look at the prompt in `generator.py` (lines 28-40). Notice these techniques:
- **Bullet Points:** Explaining exactly what we want.
- **Strict Format:** Telling the AI exactly which JSON keys to use.
- **Formatting constraints:** Using capital letters like **ONLY with raw JSON** to force compliance.

> [!IMPORTANT]
> **Today's Experiment:** Look at `main.py` lines 150-163. Notice how we define the "Representative" role. What happens if you change the "MISSION" text? The AI's behavior changes entirely!

---
*Next Up: Day 3 - Extracting Structured Data from Unstructured Text*
