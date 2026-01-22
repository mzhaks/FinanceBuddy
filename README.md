# Agentic Finance Firm – Setup Guide

This repository contains a multi-agent finance system with RAG ingestion, Qdrant vector database, and LangGraph + LangSmith integration.

Follow the steps **exactly in order**.

---

## Clone the Repository

```bash
git clone <your-repository-url>
cd <your-repository-name>
```

---

## Environment Setup

Create a `.env` file in the root directory and add the following:

```env
GOOGLE_API_KEY="add_api_key"

LANGSMITH_API_KEY="add_api_key"
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT="https://api.smith.langchain.com"
LANGCHAIN_PROJECT="multi-agent-system"

OLLAMA_API_KEY="add_api_key"
QDRANT_API_KEY="add_api_key"
```

---

## Start Qdrant and Backend Services

```bash
cd Agentic-Finance-Firm
docker compose up -d
```

---

## Install Python Dependencies

```bash
uv add -r ./requirements.txt
```

---

## Run Data Ingestion Pipelines

```bash
cd ../Agenticrag_ingestion
```

Run the notebooks in **this exact order**:

1. `Docling_data_extraction.ipynb`
2. `image_description.ipynb`
3. `Final_data_ingestion.ipynb`

---

## Start the Agentic System

```bash
cd ../Agentic-Finance-Firm
langgraph dev
```

---

## Open LangSmith UI

After starting `langgraph dev`, open the **LangSmith URL printed in the terminal** to view the agent system, traces, and workflows.

---

## System Ready

Qdrant is running, data is ingested, agents are live, and LangSmith tracing is enabled.

🚀 Agentic Finance Firm is now running.