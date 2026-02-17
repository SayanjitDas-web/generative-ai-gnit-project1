# 🎓 Day 4: Introduction to LangChain & State Systems

As we move from single prompts to complex apps, we need a way to organize our code. That's where **LangChain** and **State Systems** come in.

## 🔗 What is LangChain?
LangChain is a framework that makes working with AI easier. Instead of writing complex API calls to OpenAI, we use LangChain's standard objects:
- `ChatOpenAI`: The model interface.
- `HumanMessage` / `SystemMessage`: Standardized inputs.
- `invoke()`: The command to run the AI.

## 📦 The "State" Concept
When we build an AI workflow, we need a way to pass data between steps. Imagine a relay race where the baton is the "State". 

In `generator.py` (line 11), we define our baton:
```python
class GraphState(TypedDict):
    resume_text: str       # The raw input
    structured_data: Dict  # The JSON we extracted (Day 3)
    portfolio_content: Dict # The creative copy we will write
    error: str             # Any problems that happened
```

## 🧠 Why `TypedDict`?
By using a `TypedDict`, we guarantee that every part of our AI "Brain" knows exactly what data it's working with. If one step breaks, the `error` field in the State will let us know.

> [!NOTE]
> **Key Insight:** Generative AI is unpredictable. High-quality systems use "States" to keep track of what the AI has done and what it still needs to do.

---
*Next Up: Day 5 - LangGraph: The Brain of our Automation*
