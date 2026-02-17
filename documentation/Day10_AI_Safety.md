# 🎓 Day 10: AI Safety & Deployment (System Prompts & Boundaries)

Congratulations! You’ve reached Day 10. Today we talk about the most important part of any AI app: **Reliability and Safety**.

## 🛑 Setting Strict Boundaries
An AI assistant can be tricked into saying weird things. We prevent this using **System Prompts**.
Look at `main.py` lines 154-158:
- **Rule 1:** ONLY career-related answers.
- **Rule 2:** DECLINE off-topic questions.
- **Rule 3:** Don't have info? SAY you don't have it.

## 🛡️ Preventing "Hallucinations"
Hallucinations happen when an AI makes up facts. By telling the AI "If asked about something NOT in the Resume Context, say you don't have that information," we force it to be honest.

## 🚀 Future-Proofing
Notice how we allow users to provide their *own* `openrouter_key` in the dashboard. This:
1. **Reduces Cost:** You don't pay for everyone's usage.
2. **Increases Privacy:** Users use their own accounts.
3. **Improves Reliability:** Each user has their own API limits.

---

## 🎉 Workshop Complete!
You now have a system that:
- [x] Parses PDF Resumes.
- [x] Orchestrates complex AI tasks with **LangGraph**.
- [x] Uses **Vector Databases** for long-term memory.
- [x] Maintains a professional, safe **Chat Representative**.

**Next Steps:** Try changing the models to `anthropic/claude-3-haiku` in `generator.py` and see how the writing style changes!

---
*Happy Coding! ✨*
