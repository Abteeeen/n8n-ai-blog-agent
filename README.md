<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=220&section=header&text=AI%20Auto-Blogger&fontSize=80&animation=fadeIn&fontAlignY=35&desc=Research%20•%20Analyze%20•%20Draft%20•%20Publish&descAlignY=55&descAlign=50" />
</div>

<div align="center">
  
  ![n8n](https://img.shields.io/badge/n8n-FF6584?style=for-the-badge&logo=n8n&logoColor=white)
  ![Notion](https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white)
  ![Google Gemini](https://img.shields.io/badge/Google%20Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)
  ![Llama 3.1](https://img.shields.io/badge/Llama%203.1-0467DF?style=for-the-badge&logo=meta&logoColor=white)
  ![SerpApi](https://img.shields.io/badge/SerpApi-000000?style=for-the-badge&logo=google&logoColor=white)

</div>

---

# ✍️ Autonomous SEO Blog Writer

An advanced **n8n automation workflow** that acts as a full-stack content team. It researches keywords on Google, determines user intent (How-to vs. Comparison vs. Listicle) using **Llama 3.1**, and drafts high-quality, SEO-optimized articles using **Google Gemini 2.5 Flash** directly into **Notion**.

## 🚀 Key Features

* **🔍 Smart Research:** Uses **SerpApi** to scrape the Top 5 organic Google results for any given keyword.
* **🧠 Intent Classification:** Uses **Llama 3.1 (via Groq)** to analyze search results and decide the best article structure (e.g., *Is this a "How-to" guide or a "Best of" list?*).
* **📝 Adaptive Drafting:** dynamically fetches specific prompts from Notion based on the article type (e.g., specialized prompts for "Comparison" articles).
* **🎨 Notion Formatting:** A custom JavaScript "Chunker" converts Markdown output into native **Notion Blocks** (Headings, Bullet points, Paragraphs) for a perfect publishing experience.
* **🤖 Multi-LLM Agent:** Orchestrates multiple AI models (Llama for logic/routing, Gemini for creative writing) for optimal cost and performance.

## 🛠️ Architectures

```mermaid
graph TD
    A["Start: Webhook / Slack / Notion"] --> B["Fetch Keywords from Notion DB"]
    B --> C["🕵️ Google Search (SerpApi)"]
    C --> D{"🧠 Llama 3.1: Analyze Intent"}
    D -- "How-to" --> E["Gemini: How-to Writer"]
    D -- "Comparison" --> F["Gemini: Comparison Writer"]
    D -- "Listicle" --> G["Gemini: Listicle Writer"]
    D -- "Why-is" --> H["Gemini: Explainer Writer"]
    E & F & G & H --> I["📜 Markdown Formatting"]
    I --> J["🚀 Publish to Notion Page"]
