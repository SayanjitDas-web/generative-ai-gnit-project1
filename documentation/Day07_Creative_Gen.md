# 🎓 Day 7: Creative Content Generation

Data extraction is "Analytical". Today we talk about "Creative" AI: **The Copywriter**.

## 🎨 The Transformation
Our system doesn't just copy-paste your resume. It transforms it. 
Look at `write_portfolio_node` in `generator.py` (line 53). 

### The Prompt Strategy
1. **Impact-Oriented:** We tell the AI to rewrite descriptions to be more impactful.
2. **Multi-Page Awareness:** We ask for 4 distinct sections: Home, Skills, Experience, and Projects.
3. **Structured Variety:** 
   - Home needs a "Catchy Title".
   - Skills needs "Categories".
   - Experience needs "Rewritten Descriptions".

## 🧱 The JSON Bridge
The AI returns a complex JSON object. Our front-end then loops through this JSON to create the actual web pages.

```python
# The LLM prompt asks for this specific structure:
Return as a JSON object with keys: 'home', 'skills', 'experience', 'projects'.
```

## 🛠️ Formatting Constraints
Notice the **CRITICAL** instructions in the prompt (lines 66-70). We force the AI to return data in the exact format our code expects. For example, 'skills' must be a Dictionary of Lists.

> [!TIP]
> **Why specify the format?** If the AI returns a list but our code expects a dictionary, the website will CRASH. Prompt engineering isn't just about words; it's about **Data Engineering**.

---
*Next Up: Day 8 - RAG: Giving the AI a Memory (Part 1 - Indexing)*
