# Agentic AI Course Enrollment Assistant

An end-to-end multi-agent course-enrollment assistant that combines OpenAI models, the Model Context Protocol (MCP), SQL analytics, retrieval-augmented generation (RAG), persistent data stores, and a conversational Gradio interface.

## Project Overview

The project demonstrates how multiple specialized AI agents can collaborate to answer course questions, analyze enrollment information, retrieve curriculum knowledge, preserve conversation context, and generate personalized recommendations.

The implementation is currently packaged as a Google Colab notebook for rapid experimentation and demonstration.

## Architecture

```text
User
  |
  v
Memory Agent
  |
  v
Master Orchestrator (OpenAI GPT)
  |
  +----------------+----------------+----------------+
  |                |                |                |
  v                v                v                v
SQL Agent     Analytics Agent    RAG Agent      MCP Tools
  |                |                |                |
  v                v                v                v
SQLite          DuckDB          ChromaDB       MCP Server
  \____________________   _______________________/
                       \ /
                        v
              Recommendation Agent
                        |
                        v
                  Response Agent
                        |
                        v
                    Gradio UI
```

## Key Capabilities

- Multi-agent orchestration using LangGraph
- Tool access through a real MCP server and stdio client
- OpenAI-powered orchestration, SQL generation, recommendations, and response generation
- SQL-backed course and user information with SQLite
- Analytics workflows using DuckDB
- Semantic curriculum search using ChromaDB and sentence-transformer embeddings
- Conversation memory and user-specific state
- Interactive chatbot experience using Gradio

## Tech Stack

| Layer | Technology |
|---|---|
| LLM | OpenAI GPT |
| Agent Orchestration | LangGraph |
| Tool Protocol | Model Context Protocol (MCP) |
| Operational Data | SQLite |
| Analytics | DuckDB |
| Vector Store | ChromaDB |
| Embeddings | Sentence Transformers |
| Interface | Gradio |
| Data Processing | pandas, openpyxl |
| Development | Python, Google Colab |

## Notebook

The complete implementation is available in:

**[Courseworkingwithopenai.ipynb](./Courseworkingwithopenai.ipynb)**

The notebook includes environment setup, MCP server creation, agent definitions, data stores, orchestration logic, and the interactive application.

## Getting Started

### 1. Open the notebook

Run the notebook in Google Colab or a compatible Jupyter environment.

### 2. Install dependencies

The notebook installs the required packages, including:

```bash
mcp openai duckdb chromadb sentence-transformers langgraph gradio pandas openpyxl nest_asyncio
```

### 3. Configure credentials

Provide your OpenAI API key through an environment variable or secure notebook prompt.

> Never commit API keys, credentials, or secrets to the repository.

### 4. Run the workflow

Execute the notebook cells in sequence to initialize the data stores, MCP server, agents, orchestration graph, and Gradio interface.

## What This Project Demonstrates

This project goes beyond a single chatbot prompt by combining agent orchestration, structured data access, analytics, semantic retrieval, tool calling, persistent memory, and an interactive user interface in one workflow.

It is designed as a portfolio demonstration of applied GenAI engineering and agentic system design.

## Next Improvements

- Refactor notebook components into a modular Python application
- Add automated tests for tools and agent routing
- Add Docker-based local deployment
- Add evaluation and tracing for agent responses
- Add architecture and UI screenshots
- Add CI checks with GitHub Actions

## Security

Secrets should be supplied at runtime and must never be committed to source control. Production deployments should also apply least-privilege access, input validation, logging, and appropriate data-protection controls.
