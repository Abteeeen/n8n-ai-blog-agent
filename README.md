🤖 AI Blog Writing Agent

This project is an automated "AI Writing Agency" built using **n8n**, **OpenAI/Gemini**, **Notion**, and **Slack**.

🚀 How it Works
1.  **Trigger:** I type `start` in a specific Slack channel.
2.  **Fetch:** The bot searches my **Notion Database** for topics marked "For AI Writing".
3.  **Process:**
    * A custom Javascript Chunker splits the topic into logical sections.
    * **Google Gemini** generates the content for each section.
    * The bot ensures proper Markdown formatting (Headings, Bold text).
4.  **Publish:** The bot writes the finished blog post back into Notion.
5.  **Notify:** It updates the status to "Done".

 🛠️ Tools Used
* **n8n** (Self-hosted)
* **Google Gemini API** (LLM)
* **Notion API** (CMS)
* **Slack API** (Interface)

 📸 Workflow Preview
*(You can drag and drop a screenshot of your n8n canvas here!)*
