---
title: career_conversations
app_file: app.py
sdk: gradio
sdk_version: 5.49.1 
---

 
# Career Conversations

**Project:** A conversational chatbot that represents Prabhnoor Singh and answers questions about his career, skills, and experience.

**Live Demo:** https://huggingface.co/spaces/prabhnosingh/career_conversations

**Tech Used:**
- **Python:** core language.
- **Gradio:** web chat interface (`gradio`).
- **OpenAI SDK & agents:** for LLM-driven chat and tool calls (`openai`, `openai-agents`).
- **pypdf:** extracts text from PDF resumes or LinkedIn exports (`pypdf`).
- **python-dotenv:** loads environment variables from `.env`.
- **requests:** for simple webhook/tool integrations.

**What this chatbot does / What to expect when interacting:**
- The assistant speaks as Prabhnoor Singh and uses a local summary and a LinkedIn PDF for context.
- It answers career-related questions (background, skills, experience, projects) using that context.
- If it can't answer a question, it records the unknown question for later review.
- It can ask users for an email address and record contact details via a simple webhook (used to capture interest).
- The chat is interactive and aims to be professional and informative—good for potential clients or employers.

**How it works:**
- On startup the app reads `me/summary.txt` and `me/linkedin.pdf` to build context.
- The app uses the OpenAI chat completions API with tool-calling enabled. Tool calls are handled locally (for example to record emails or unknown questions).
- `gr.ChatInterface` launches a lightweight web UI for conversations.

**Run locally:**
```bash
python -m pip install -r requirements.txt
python app.py
```

**Notes:**
- Ensure environment variables (OpenAI credentials, pushover tokens if used) are configured in a `.env` file.
- The live demo hosted on Hugging Face Spaces showcases the running app if you prefer not to run locally.
