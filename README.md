# RAG-Based Domain Chatbots

A practical Retrieval-Augmented Generation (RAG) project built with **n8n**, **Pinecone**, **Hugging Face Embeddings**, and an **AI Agent/LLM workflow**.

## Overview

This project contains two domain-specific RAG applications:

1. **IPSR Courses Knowledge Base & Recommendation Assistant**
2. **Union Budget 2026–27 Knowledge Base & Query Assistant**

The project demonstrates document ingestion, text chunking, vector embeddings, semantic retrieval, vector-store integration, conversational memory, and AI-agent-based response generation.

## Architecture

### Knowledge Base Pipeline

```text
Document Upload
      ↓
Default Data Loader
      ↓
Recursive Character Text Splitter
      ↓
Hugging Face Embeddings
      ↓
Pinecone Vector Store
      ↓
Pinecone Index
```

### Chatbot Pipeline

```text
User Message
      ↓
Chat Trigger
      ↓
AI Agent
   ↙     ↓      ↘
Memory  LLM   Vector Store
          ↓       ↓
       Response ← Pinecone
```

## Technologies

- **n8n** — workflow automation and AI orchestration
- **Pinecone** — vector database and semantic retrieval
- **Hugging Face Embeddings** — document embedding generation
- **Groq Chat Model** — language model used by the AI Agent
- **RAG (Retrieval-Augmented Generation)** — knowledge-grounded responses

## Project 1: IPSR Courses Assistant

The IPSR Courses knowledge base processes course-related source material and stores vector embeddings in Pinecone.

The assistant is designed to answer questions about:
- Courses and training programs
- Certifications
- Admissions
- Placement assistance
- Course recommendations

The workflow is designed to prioritize retrieved knowledge-base information and avoid unsupported claims.

## Project 2: Union Budget 2026–27 Assistant

A separate knowledge base was created from a Union Budget 2026–27 document.

The chatbot retrieves relevant document chunks from Pinecone and uses them to answer questions about the budget.

The workflow includes:
- Document loading
- Text splitting
- Hugging Face embeddings
- Pinecone vector storage
- Semantic retrieval
- AI-agent response generation

## Key Components

| Component | Purpose |
|---|---|
| Default Data Loader | Extracts text from uploaded documents |
| Recursive Character Text Splitter | Splits documents into smaller context-preserving chunks |
| Hugging Face Embeddings | Converts text chunks into vector representations |
| Pinecone Vector Store | Stores and retrieves embeddings |
| AI Agent | Orchestrates retrieval and response generation |
| Groq Chat Model | Generates natural-language responses |
| Simple Memory | Maintains conversational context |

## Results / Evidence

The knowledge-base workflows were successfully executed and the Pinecone indexes stored the generated embeddings. The project documentation includes screenshots of the n8n workflows and Pinecone vector databases.

## Repository Structure

```text
RAG-Domain-Chatbots/
├── README.md
├── workflows/
│   └── n8n-workflows.json
├── documentation/
│   └── project-report.pdf
├── screenshots/
│   ├── ipsr-knowledgebase.png
│   ├── ipsr-pinecone.png
│   ├── budget-knowledgebase.png
│   └── budget-pinecone.png
└── sample-data/
    └── README.md
```

## Privacy & Security

Do not commit API keys, credentials, private datasets, proprietary documents, or other confidential internship/company information.

Use environment variables or n8n credentials for secrets.

## What I Learned

- Designing RAG pipelines
- Document ingestion and preprocessing
- Text chunking for retrieval
- Generating and storing vector embeddings
- Semantic similarity search with a vector database
- Connecting retrieval tools to AI agents
- Designing prompts that prioritize retrieved source information
- Building domain-specific AI assistants with n8n

## Author

**Hannath C Shabeer**

AI & Data Science Student

GitHub: https://github.com/Hannath03
