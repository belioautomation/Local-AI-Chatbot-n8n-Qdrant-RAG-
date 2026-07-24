# 🤖 Local AI Chatbot (n8n + Qdrant + RAG)

![n8n](https://img.shields.io/badge/Automation-n8n-orange?style=for-the-badge&logo=n8n)
![RAG](https://img.shields.io/badge/Architecture-RAG-blue?style=for-the-badge)
![Qdrant](https://img.shields.io/badge/Vector%20Database-Qdrant-red?style=for-the-badge)
![AI Agent](https://img.shields.io/badge/AI-Agent-green?style=for-the-badge)
![OpenRouter](https://img.shields.io/badge/LLM-OpenRouter-purple?style=for-the-badge)
![Docker](https://img.shields.io/badge/Deployment-Docker-blue?style=for-the-badge&logo=docker)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow?style=for-the-badge)

A **Local AI Chatbot powered by n8n, Qdrant Vector Database, and Retrieval-Augmented Generation (RAG)**.

This project demonstrates how to build a private AI assistant capable of understanding and answering questions from custom documents.

Instead of relying only on an AI model's existing knowledge, the system retrieves relevant information from a self-managed knowledge base and uses it as context to generate more accurate responses.

---

# 📌 Project Overview

The project is designed as a modular AI system containing three major workflows:

| Part | Workflow | Status |
|---|---|---|
| Part 1 | 📚 Knowledge Base Indexer | ✅ Completed |
| Part 2 | 💬 Local AI Chatbot | ✅ Completed |
| Part 3 | 🗂️ Knowledge Base Manager | 🚧 In Progress |

The architecture follows the **RAG (Retrieval-Augmented Generation)** pattern:

```

```
            Documents
                |
                v
    Knowledge Base Indexer
            (Part 1)
                |
                v
        Vector Embeddings
                |
                v
          Qdrant Database
                |
                v
         Local AI Chatbot
            (Part 2)
                |
                v
          AI Generated Answer
```

```

---

# 🏗️ System Architecture

The entire workflow is built using **n8n as the automation layer**.

```

```
                     ┌─────────────────────────┐
                     │ Knowledge Base Indexer  │
                     │        Part 1           │
                     └────────────┬────────────┘
                                  |
                                  |
                                  v
                         ┌────────────────┐
                         │ Qdrant Vector  │
                         │   Database     │
                         └────────────────┘
                                  |
                                  |
                                  v
                     ┌─────────────────────────┐
                     │    Local AI Chatbot     │
                     │        Part 2           │
                     └────────────┬────────────┘
                                  |
                                  |
                                  v
                          AI Response


                     ┌─────────────────────────┐
                     │ Knowledge Base Manager  │
                     │        Part 3           │
                     │     🚧 Development      │
                     └─────────────────────────┘
```

```

---

# 📚 Part 1: Knowledge Base Indexer ✅ Completed

## Overview

The Knowledge Base Indexer is responsible for converting uploaded documents into searchable AI knowledge.

It processes documents, extracts information, splits content into smaller chunks, creates embeddings, and stores them inside Qdrant.

---

## Workflow

```

Document Upload
|
v
Download File
|
v
Extract Document Content
|
v
Split Text Into Chunks
|
v
Generate Embeddings
|
v
Store Vectors in Qdrant
|
v
Send Notification

```

---

## Features

✅ Detect uploaded documents  
✅ Download files automatically  
✅ Extract text content  
✅ Create document chunks  
✅ Generate vector embeddings  
✅ Store embeddings in Qdrant  
✅ Prepare knowledge base for AI retrieval  

---

## Technologies Used

- n8n
- Qdrant
- Embedding Models
- Document Processing Nodes
- Google Drive Integration

---

# 💬 Part 2: Local AI Chatbot ✅ Completed

## Overview

The Local AI Chatbot allows users to communicate with the knowledge base using natural language.

The chatbot follows the RAG process:

1. Receive user question
2. Understand user intent
3. Search relevant information from Qdrant
4. Retrieve matching document chunks
5. Generate AI response using retrieved context

---

## Workflow

```

User Question
|
v
AI Agent
|
v
Intent Router
|
v
Create Query Embedding
|
v
Search Qdrant Database
|
v
Retrieve Relevant Context
|
v
Generate Final Answer

```

---

## Features

✅ AI Agent integration  
✅ Intent classification  
✅ Semantic document search  
✅ Qdrant vector retrieval  
✅ Context-based responses  
✅ RAG implementation  

---

## Example

### User Question

```

What is the objective of the Knowledge Base Indexer?

```

### AI Response

```

The objective of the Knowledge Base Indexer is to create and maintain an indexed representation of knowledge base content, enabling fast and efficient search, retrieval, and organization of information.

```

---

# 🗂️ Part 3: Knowledge Base Manager 🚧 In Progress

## Overview

The Knowledge Base Manager will provide administrative control over the stored knowledge.

This component is planned to manage the lifecycle of documents and vectors inside the knowledge base.

---

## Planned Features

🚧 Add new knowledge sources  
🚧 Remove outdated documents  
🚧 Update indexed content  
🚧 Manage Qdrant collections  
🚧 Monitor knowledge base health  
🚧 Provide database management interface  

---

## Current Status

The workflow structure has been created, but implementation is still ongoing.

Future updates will complete the knowledge management system.

---

# 🧠 How RAG Works in This Project

## 1. Retrieval Phase

The system searches the vector database.

```

User Query

```
  |
  v
```

Embedding Generation

```
  |
  v
```

Vector Similarity Search

```
  |
  v
```

Relevant Documents Retrieved

```

---

## 2. Generation Phase

The retrieved information is provided to the AI model.

```

Retrieved Context
+
User Question

```
    |
    v
```

LLM Processing

```
    |
    v
```

Final Answer

```

---

# 🛠️ Technology Stack

| Technology | Purpose |
|-|-|
| n8n | Workflow automation and AI orchestration |
| Qdrant | Vector database for semantic search |
| OpenRouter | LLM access layer |
| RAG | Knowledge retrieval architecture |
| Embeddings | Convert text into vectors |
| Docker | Local deployment environment |

---

# 📂 Project Structure

```

Local-AI-Chatbot-RAG
│
├── Knowledge-Base-Indexer
│   └── n8n workflow
│
├── Local-AI-Chatbot
│   └── n8n workflow
│
├── Knowledge-Base-Manager
│   └── n8n workflow
│
├── screenshots
│   └── workflow-preview.png
│
└── README.md

```

---

# 📸 Workflow Demo

The workflow demo shows the complete AI pipeline:

### Part 1 - Knowledge Base Indexing

- Upload documents
- Extract content
- Generate embeddings
- Store vectors in Qdrant


### Part 2 - AI Chatbot

- Ask questions
- Retrieve knowledge
- Generate AI responses


### Part 3 - Knowledge Base Manager

🚧 Currently under development.

---

# 🎯 Possible Use Cases

This architecture can be adapted for:

- 📚 Personal AI knowledge assistant
- 🎓 AI study assistant
- 📄 Document analysis chatbot
- 🏢 Internal company knowledge system
- 📖 Research assistant
- 💻 Developer documentation chatbot
- 🗂️ Enterprise knowledge management

---

# 🚀 Future Improvements

Planned improvements:

- Complete Knowledge Base Manager
- Add authentication
- Add web-based chatbot interface
- Add document metadata management
- Improve retrieval accuracy
- Add conversation memory
- Add more local AI models

---

# 📖 What I Learned

Building this project helped me understand:

- Retrieval-Augmented Generation architecture
- Vector databases
- Embedding systems
- AI agent workflows
- Document processing pipelines
- Local AI deployment
- Modular automation design

---

# 👨‍💻 Author

**Belio C. Sinangote**

AI Automation Developer  
n8n Workflow Builder | RAG Enthusiast

GitHub:
https://github.com/belioautomation

---
