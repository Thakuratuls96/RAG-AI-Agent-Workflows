# Embedding Workflow

This workflow is used to **take documents and save their data in Pinecone** so that an AI can later answer questions from those documents.

This workflow must be run **before** the RAG Answer workflow.

---

## What this workflow does

This n8n workflow:

1. Watches Google Drive for new files.
2. Downloads the file content.
3. Extracts text from the file.
4. Converts the text into embeddings using **Google Gemini**.
5. Stores those embeddings in **Pinecone**.

After this, the document data is ready to be searched by the AI.

---

## Why this workflow is needed

- AI cannot read documents directly.
- Documents must first be converted into embeddings.
- These embeddings are stored in Pinecone for fast searching.
- Without this workflow, the AI cannot answer document-based questions.

---

## Tools Used

- n8n
- Google Drive
- Google Gemini (Embeddings)
- Pinecone Vector Database

---

## Workflow Steps

| Step | Description |
|----|----|
| Trigger | Detects new files in Google Drive |
| Download | Gets the file content |
| Text Extract | Reads text from the document |
| Embedding | Converts text into vectors |
| Store | Saves vectors in Pinecone |

---

## Input & Output

**Input:**  
- PDF or text documents from Google Drive

**Output:**  
- Vector data stored in Pinecone

## Workflow Diagram

![RAG Answer Workflow Diagram](./ss/workflow%201.pngrag-answer-workflow.png)

---