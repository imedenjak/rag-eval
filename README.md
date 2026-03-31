# RAG Eval

A RAG (Retrieval-Augmented Generation) evaluation pipeline using LangChain, OpenAI, and LangSmith.

## What it does

- Loads documents from web URLs using `WebBaseLoader`
- Splits them into chunks and indexes them in an in-memory vector store using OpenAI embeddings
- Exposes a `rag_bot` function that retrieves relevant chunks and answers questions via GPT-4.1
- Evaluates answer correctness against a reference dataset stored in LangSmith

## Setup

### 1. Install dependencies

```bash
uv sync
```

### 2. Configure environment variables

Copy `.env.example` to `.env` and fill in your API keys:

```bash
cp .env.example .env
```

### 3. Run the notebook

Open `main.ipynb` in VS Code or Jupyter and run the cells.

## Notes

- If you are in the EU, set `LANGSMITH_ENDPOINT` to `https://eu.api.smith.langchain.com` and make sure your LangSmith API key was generated on the EU instance (app.eu.smith.langchain.com).
- The LangSmith dataset is created on first run. If you re-run, the existing dataset will be deleted and recreated.