# AI Web Scraping Semantic Search RAG Pipeline

## Overview

This project demonstrates an end-to-end **Retrieval-Augmented Generation (RAG)** workflow integrating web scraping, document preprocessing, semantic embeddings, vector databases, and local large language models.

The solution collects publicly available web content, transforms text into embeddings using **SentenceTransformers**, stores vectors inside **ChromaDB**, and enables semantic retrieval using **OpenWebUI** and **Ollama**.

This project was developed for **Case Study 8 — Web Scraping to Vector Database**.

---

## Technologies Used

* Python
* Jupyter Notebook
* LangChain
* ChromaDB
* SentenceTransformers
* Transformers
* Docker
* Ollama
* OpenWebUI
* NumPy
* dotenv

---

## Project Architecture

Web Scraping → Text Processing → Chunking → Embedding Generation → Vector Storage → Semantic Retrieval

### Pipeline Workflow

1. Scrape publicly accessible websites.
2. Extract and preprocess text content.
3. Split documents into chunks.
4. Generate semantic embeddings using SentenceTransformers.
5. Store embeddings inside ChromaDB.
6. Perform semantic search and contextual retrieval using OpenWebUI + Ollama.

---

## Selected URLs

Example data sources used within the project included:

* Wikipedia — Artificial Intelligence
* Reuters Technology
* Microsoft Azure AI Services Documentation

All selected sources were:

* Publicly accessible
* English language content
* Different domains
* Text-rich webpages

---

## Environment Setup

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Launch ChromaDB

```bash
docker run -d \
--name chromadb-server \
-p 8000:8000 \
-v ~/chromadb-data:/chroma/chroma \
-e ANONYMIZED_TELEMETRY=False \
chromadb/chroma:latest
```

### 3. Verify ChromaDB

Open:

```text
http://localhost:8000/api/v2/heartbeat
```

### 4. Start Ollama

```bash
ollama run llama3.2
```

### 5. Launch OpenWebUI

```bash
docker run -d \
-p 3000:8080 \
--add-host=host.docker.internal:host-gateway \
-v open-webui:/app/backend/data \
ghcr.io/open-webui/open-webui:main
```

---

## Results

Project execution successfully demonstrated:

* Successful web scraping pipeline
* Document chunk generation
* Semantic embedding creation
* ChromaDB vector storage
* Local LLM semantic retrieval
* OpenWebUI query validation

Pipeline Results:

* **276 processed documents**
* **384-dimension embeddings**
* Successful vector database verification
* Working semantic search interface

---

## Repository Structure

```text
AI-WebScraping-SemanticSearch-RAG/
│
├── DariousBrown_WebScraping_VectorDB_RAG.ipynb
├── README.md
├── requirements.txt
├── .env.example
├── .gitignore
│
├── screenshots/
│   ├── chromadb_heartbeat.png
│   ├── docker_containers.png
│   ├── ollama_models.png
│   ├── openwebui_interface.png
│   └── OpenWebUI_VectorDatabase_Retrieval_Test.png
│
└── docs/
    └── DariousBrown_WebScraping_Challenge_Report.docx
```

---

## Screenshots

Example project validation screenshots are included within the `screenshots/` folder.

Included evidence:

* Docker containers running
* ChromaDB heartbeat verification
* OpenWebUI interface
* Semantic retrieval testing
* Vector database verification

---

## Author

**Darious Brown**
PhD — Artificial Intelligence & Machine Learning
Portfolio: https://dare215.github.io/DariousBrown-Portfolio/
