# RAG Chatbot - Chat with PDFs Locally

A local RAG (Retrieval-Augmented Generation) chatbot that lets you chat with multiple PDF documents.

![Demo](assets/demo.png)

## Features

- Chat with multiple PDF documents locally
- Supports models from **Huggingface** and **Ollama**
- Simple UI built with **Gradio**
- Docker support for easy deployment

## How It Works

![RAG Flow](./assets/rag-flow.svg)

![Retriever](./assets/retriever.svg)

## Setup

### Prerequisites

Install `uv` package manager:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

> Ensure `~/.local/bin` is on your `PATH`.

### Option 1: Docker (Recommended)

```bash
docker compose up --build
```

### Option 2: Manual Installation

#### 1. Install Ollama

- **macOS/Windows**: [Download here](https://ollama.com/)
- **Linux**:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### 2. Install Ngrok (Optional - for remote access)

- **macOS**:
```bash
brew install ngrok/ngrok/ngrok
```

- **Linux**:
```bash
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc \
| sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
&& echo "deb https://ngrok-agent.s3.amazonaws.com buster main" \
| sudo tee /etc/apt/sources.list.d/ngrok.list \
&& sudo apt update \
&& sudo apt install ngrok
```

#### 3. Install Python Dependencies

```bash
uv sync --locked
```

## Running the App

```bash
bash ./scripts/run.sh
```

Or run directly:

```bash
uv run python -m rag_chatbot --host localhost
```

With Ngrok (for remote access):

```bash
bash ./scripts/run.sh --ngrok
```

## Access

Open your browser and go to: `http://localhost:7860/`
