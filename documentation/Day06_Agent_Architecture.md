# 🎓 Day 6: Building Your First Agent Architecture

Yesterday we saw the Graph structure. Today, let's talk about **Architecture**.

## 🏗️ The "Worker" Pattern
In our app, we use a "Sequential Worker" pattern. Each node is like a specialist worker in a factory.

### Worker 1: The Librarian (`extract_resume_node`)
- **Skill:** Organization.
- **Job:** Turn a messy pile of words into a structured file.

### Worker 2: The Creative Copywriter (`write_portfolio_node`)
- **Skill:** Creativity.
- **Job:** Look at the organized file and write catchy headlines for a website.

## 🤝 The "Wrapper" Pattern
In `generator.py` (lines 89-93), you'll see "wrappers":
```python
def extract_wrapper(state):
    return extract_resume_node(state, state.get("api_key"))
```
**Why do we do this?**
LangGraph expects functions to take *only* the `state`. But our functions might need an `api_key`. The wrapper acts as a bridge!

## 🚀 Compiling the Brain
Finally, we `compile()` the graph (line 102). This turns our list of rules into a "Runnable" application.

```python
app_graph = workflow.compile()
```

> [!TIP]
> **Architecture is key:** By separating "Extracting" from "Writing", we can improve one without breaking the other. This is a best practice in AI engineering.

---
*Next Up: Day 7 - Advanced Content Gen (Creative Writing with LLMs)*
