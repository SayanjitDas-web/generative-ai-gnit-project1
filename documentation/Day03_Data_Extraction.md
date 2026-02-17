# 🎓 Day 3: Extracting Structured Data from Unstructured Text

Yesterday we learned about prompts. Today, we look at a "Real World" problem: **How do we turn a messy PDF resume into neat JSON data?**

## 📄 The Challenge
A PDF contains text, but it’s just a long string. To build a website, we need specific fields: `full_name`, `skills`, `projects`, etc.

## 🛠️ The Solution: `extract_resume_node`
In `generator.py` (line 25), we have a function called a "Node". This node's only job is to **Parse**.

### How it works:
1. **Input:** Raw text from the PDF.
2. **Prompt:** We give the AI a template of the JSON we want.
3. **Execution:** The LLM fills in the blanks.
4. **Cleanup:** Since LLMs sometimes add extra text (like "Here is your JSON:"), we use professional "stripping" to get only the code.

```python
# Cleaning the LLM output in generator.py
data = json.loads(response.content.strip("```json").strip("```"))
```

## 🧠 Why is this "Generative AI"?
We aren't just searching for keywords. If the resume says "I managed a team of 5", the AI understands that goes under **Experience** without you writing a single "Regex" or "if" statement.

### Key Fields We Extract:
- **Contact Info:** Phone, Email, LinkedIn.
- **Skills:** A simple list of tools.
- **Project Objects:** Name, Stack, and Description.

> [!TIP]
> **Try this:** Look at `generator.py` line 43. Notice how we tell the AI to ensure lists are of **Dictionaries**. This is crucial for our front-end blocks!

---
*Next Up: Day 4 - Introduction to LangChain & State Systems*
