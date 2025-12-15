# RAG-AI-Agent-Workflows

This repository contains two n8n workflows for building a RAG-based AI assistant using:

- **Google Gemini** (LLM)
- **Pinecone** (Vector Database)
- **n8n** (Automation)

## Workflows

### 1. Embedding Workflow
**Folder:** `1-Embedding-Workflow`

- Watches Google Drive for new files.
- Downloads file content.
- Converts text into embeddings using Google Gemini.
- Stores embeddings in Pinecone Vector Store.
- Prepares data for RAG-based queries.

### 2. RAG Answer Workflow
**Folder:** `2-RAG-Answer-Workflow`

- Receives user questions via chat/webhook.
- Converts query into embedding.
- Searches Pinecone for relevant documents.
- Uses Google Gemini to generate context-aware answers.
- Returns answer to user.

> ⚠️ **Note:** Gemini injects warning/disclaimer text by default (e.g., “fees may vary…”). This does **not break the workflow**. Optional post-processing can remove it.

## Getting Started

1. Clone the repo.
2. Install n8n and activate workflows.
3. Create `.env` files with your API keys (`Google Gemini`, `Pinecone`).
4. Import workflows in n8n.
5. Test embeddings workflow first, then RAG workflow.

