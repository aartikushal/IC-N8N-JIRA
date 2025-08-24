# 📝 Jira Docs Helper

The **Jira Docs Helper** is an AI-powered assistant that makes it easier for teams to interact with their Jira project documentation and tickets using **natural language queries**.  

Instead of manually searching through Jira dashboards, team members can query the bot in **Telegram** and get instant, context-aware answers about tickets, stories, and progress.  

The system uses **n8n** for workflow automation, **Pinecone** for semantic search, **OpenAI embeddings + chat models** for natural language understanding, and connects to **Jira Docs** as the knowledge source.  

---

## 🚀 Features
- 🔎 **Semantic Jira Search** – Ask about tickets, status, or story details in plain English.  
- 📊 **Ticket Status Queries** – Check if a ticket is *in progress*, *pending*, or *resolved*.  
- 🧑‍💻 **Story Details** – Retrieve tickets based on type (frontend/backend/bug/etc.).  
- 💬 **Telegram Bot Interface** – Query Jira instantly without opening the Jira dashboard.  
- 🔗 **n8n Workflow** – Automates query → semantic search → Jira lookup → response pipeline.  

---

## 🛠️ Tech Stack
- [n8n](https://n8n.io/) – Workflow automation  
- [Pinecone](https://www.pinecone.io/) – Vector database for semantic queries  
- [OpenAI](https://platform.openai.com/) – Embeddings + LLM for NLP  
- [Telegram Bot API](https://core.telegram.org/bots/api) – Messaging platform  
- [Jira](https://www.atlassian.com/software/jira) – Ticket & project management  

---

## 📊 Architecture Flow
flowchart TD
    A[User asks Jira question in Telegram] --> B[Telegram Bot]
    B --> C[n8n Webhook]
    C --> D[OpenAI Embedding]
    D --> E[Pinecone Vector DB]
    E --> F[Relevant Jira Docs + Tickets]
    F --> G[OpenAI Chat Model]
    G --> H[Generate Answer]
    H --> I[Send Response to User in Telegram]
    C -->|Optional| J[Jira API + Docs]


Usage

Once connected, you can ask Jira-related queries directly in Telegram.

💬 Example Questions to Ask

Which story involves frontend development?

📌 Bot finds and lists tickets tagged with frontend work.

Which ticket is in progress?

📌 Bot retrieves tickets currently in In Progress status.

Which ticket is pending?

📌 Bot shows tickets with To Do or Pending status.

How many tickets are resolved?

📌 Bot counts tickets in Resolved/Done state.

🔮 Future Improvements

✅ Support for priority-based queries (e.g., "show high priority bugs").

✅ Daily/weekly status summary reports.

✅ Export ticket summaries as PDF/Excel.

✅ Integration with Slack and MS Teams.

🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.
