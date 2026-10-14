# ai-student-assistant
# AI Study Assistant 

**An AI-powered study automation system that transforms college course PDFs into structured, personalized study materials using Telegram, n8n, Python, and Obsidian.**

>  **Project status: Early development**
>
> This project is currently under development. The architecture and planned features are documented below. Features will be marked as implemented only after they have been developed and tested.

## Project Overview

As a college student studying Computer Engineering and Networks, I regularly receive course PDFs from classmates. Organizing these documents, identifying the correct academic module, summarizing the content, and preparing revision materials can take a significant amount of time.

The goal of this project is to automate this process by building a personal AI study assistant connected to my existing Obsidian knowledge base.

Instead of manually processing every document, I want to send a PDF to a Telegram bot and let the system analyze it, identify the relevant module, generate useful study materials, and save everything in the correct location in my Obsidian vault.

**The objective is not simply to summarize PDFs, but to build a context-aware learning assistant that connects new course materials with knowledge I have already collected.**

## ✨ Planned Features

-  **PDF Processing:** Extract text and page information from uploaded course documents.
-  **Telegram Integration:** Submit PDFs and receive processing updates through a Telegram bot.
-  **Intelligent Module Classification:** Identify which academic module a document belongs to using its content and my existing notes.
-  **Knowledge Retrieval:** Find relevant concepts and related materials from my Obsidian vault.
-  **AI-Generated Study Materials:** Create structured summaries, essential definitions, explanations, questions and answers, QCMs, exercises, and revision sheets.
-  **Automatic Note Organization:** Save generated Markdown files in the appropriate module folder.
-  **Obsidian Integration:** Connect new materials with existing notes using internal links.
-  **Workflow Automation:** Use n8n to coordinate processing, notifications, and error handling.
-  **Reliable Processing:** Add duplicate detection, confidence checks, logging, and error recovery.
-  **Continuous Availability:** Eventually deploy the system so it can operate independently of my laptop.

These are project goals, not a claim that all features are already implemented.

##  Planned Architecture

```
        Telegram Bot
             |
             v
       n8n Workflow
             |
             v
      Python / FastAPI
             |
             v
       PDF Processing
             |
             v
    Obsidian Knowledge Base
             |
             v
    AI Module Classification
             |
             v
    Study Material Generation
             |
             v
      Obsidian Vault
             |
             v
    Telegram Notification
```

### Technology Stack

Python – Core processing and application logic
FastAPI – Backend API
n8n – Workflow orchestration and automation
Telegram Bot API – User interaction and PDF submission
Obsidian – Personal academic knowledge base
AI model API – Document classification and study material generation
pypdf – PDF text extraction
OCR tools – Planned support for scanned PDFs

Additional technologies, such as embeddings and vector databases, may be introduced if they provide a practical benefit.

##  Expected Workflow

1. Receive a course PDF through Telegram.
2. Validate the document and extract its text.
3. Analyze its title, headings, keywords, and concepts.
4. Compare its content with the modules and notes in Obsidian.
5. Identify the most likely module and request confirmation when necessary.
6. Retrieve relevant existing notes to provide context to the AI.
7. Generate structured study materials grounded in the course content.
8. Save the resulting Markdown files in the correct module folder.
9. Notify the user through Telegram when processing is complete.

For the initial version, PDFs will be sent manually from WhatsApp to Telegram. Automatic WhatsApp group monitoring is outside the initial scope.

##  Planned Project Structure

```text
ai-study-assistant/
├── app/
│   ├── main.py
│   ├── config.py
│   ├── services/
│   │   ├── pdf_service.py
│   │   ├── vault_service.py
│   │   ├── classifier.py
│   │   ├── ai_service.py
│   │   └── study_generator.py
│   └── prompts/
├── data/
├── tests/
├── workflows/
├── .env.example
├── .gitignore
├── requirements.txt
└── README.md
```

The structure will evolve as the project develops.


### Prerequisites

- Python 3.10 or newer
- Git
- An existing Obsidian vault
- An n8n instance
- A Telegram bot
- An AI model API key for the AI integration phase



---

*Built as a personal project to make studying more organized, efficient, and context-aware.*
