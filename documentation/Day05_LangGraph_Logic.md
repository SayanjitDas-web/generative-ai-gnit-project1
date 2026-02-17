# 🎓 Day 5: LangGraph: The Brain of our Automation

Today, we meet the MVP of our project: **LangGraph**.

## 🕸️ What is a Graph?
In coding, a "Graph" is a set of **Nodes** (actions) connected by **Edges** (paths).
In our project, our graph looks like this:
1. **Node "extract":** Takes resume text -> Makes JSON.
2. **Path (Edge):** Moves to the next step.
3. **Node "write":** Takes JSON -> Writes web content.

## 🛠️ Defining the Workflow
In `generator.py` (line 87), we build this brain:
```python
workflow = StateGraph(GraphState)

# 1. Add our actions
workflow.add_node("extract", extract_wrapper)
workflow.add_node("write", write_wrapper)

# 2. Connect the dots
workflow.set_entry_point("extract")
workflow.add_edge("extract", "write")
workflow.add_edge("write", END)
```

## 🔄 State Persistence
The magic of LangGraph is that it automatically updates the state. When `extract` finishes, its output is merged into the `GraphState`. Then `write` starts with all the data `extract` just saved!

> [!IMPORTANT]
> **Wait, why use a graph?** Why not just call two functions?
> Graphs allow us to add **Loops**. If the extraction fails, we could add an edge that goes *backward* to retry with a better prompt. That's true AI automation!

---
*Next Up: Day 6 - Building Your First Agent Architecture*
