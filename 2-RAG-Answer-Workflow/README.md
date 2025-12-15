# RAG Answer Workflow

This workflow is used to **answer user queries using RAG (Retrieval-Augmented Generation)** by fetching relevant document embeddings from **Pinecone** and generating context-aware answers using **Google Gemini**.

This workflow should be run **after** the Embedding Workflow has populated Pinecone with document embeddings.

---

## What this workflow does

This n8n workflow:

1. Receives a user query via a webhook or chat input  
2. Converts the query into embeddings using **Google Gemini**  
3. Searches **Pinecone** for relevant document embeddings  
4. Combines retrieved documents with the user query as context  
5. Generates a precise, context-aware answer using **Google Gemini**  
6. Returns the answer to the user  

---

## Why this workflow is important

- Allows AI to **provide answers grounded in your documents**  
- Ensures **accurate, context-based responses**  
- Enables full **RAG pipeline** when used with the Embedding Workflow  
- Without this workflow, queries cannot retrieve knowledge from your documents  

---

## Tools Used

- n8n  
- Google Gemini (Embeddings & LLM)  
- Pinecone Vector Database  

---

## Workflow Steps

| Step | What happens |
|-----|-------------|
| Trigger | Receives user query via webhook or chat input |
| Query Embedding | Converts user query into embeddings |
| Pinecone Search | Finds most relevant document embeddings |
| Context Integration | Combines retrieved documents with user query |
| AI Response | Generates answer using Google Gemini |
| Output | Returns answer to user |

---

## Input & Output

**Input**  
- User query (text)  

**Output**  
- Context-aware answer based on documents in Pinecone  

---

## Workflow Diagram

![RAG Answer Workflow Diagram](./ss/workflow%201.png)


---

## Notes

- Run this workflow **after the Embedding Workflow**  
- Ensure **Pinecone index is populated** with document embeddings  
- This workflow **does not handle document ingestion**—use the Embedding Workflow for that  
- Use clear, specific queries for best results  
