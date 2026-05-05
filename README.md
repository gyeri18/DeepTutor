# DeepTutor

An intelligent tutoring system powered by large language models, forked from [HKUDS/DeepTutor](https://github.com/HKUDS/DeepTutor).

## Overview

DeepTutor is an AI-powered educational assistant that helps users learn and understand complex topics through interactive conversations, document analysis, and adaptive tutoring.

## Features

- 📚 **Document-based Q&A**: Upload PDFs and ask questions about their content
- 🤖 **Multi-LLM Support**: Compatible with OpenAI, Anthropic, and local models
- 💬 **Interactive Tutoring**: Adaptive conversations that guide learning
- 🔍 **RAG Pipeline**: Retrieval-Augmented Generation for accurate, grounded responses
- 🐳 **Docker Support**: Easy deployment with Docker and Docker Compose

## Prerequisites

- Python 3.10+
- Docker & Docker Compose (for containerized deployment)
- API keys for your chosen LLM provider

## Quick Start

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/DeepTutor.git
   cd DeepTutor
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your API keys and configuration
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

### Docker Deployment

1. **Configure environment**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

2. **Build and start containers**
   ```bash
   docker compose up --build
   ```

3. **Access the application**
   Open your browser and navigate to `http://localhost:7860`

## Configuration

See `.env.example` for all available configuration options, including:

- LLM provider and model selection
- Embedding model configuration
- Vector database settings
- Authentication settings

For users in China, see `.env.example_CN` for region-specific configuration.

## Project Structure

```
DeepTutor/
├── app.py              # Main application entry point
├── requirements.txt    # Python dependencies
├── Dockerfile          # Container build instructions
├── docker-compose.yml  # Multi-container orchestration
├── .env.example        # Environment variable template
└── .env.example_CN     # China-specific configuration template
```

## Personal Notes

> **Note (personal fork):** I'm using this primarily to experiment with local Ollama models. If you're doing the same, make sure to set `LLM_PROVIDER=ollama` and `OLLAMA_BASE_URL=http://localhost:11434` in your `.env` file. Works well with `llama3` and `mistral`.
>
> **Ollama tip:** I've found that setting `OLLAMA_NUM_CTX=8192` in your Ollama model config noticeably improves responses on longer documents — the default context window is too small for most PDFs.
>
> **Model note:** After more testing, `mistral` has been my go-to for tutoring tasks — it handles follow-up questions better than `llama3` in my experience. For summarization of dense academic PDFs, `llama3` still edges it out though.

## Contributing

We welcome contributions! Please check our [issue templates](.github/ISSUE_TEMPLATE/) for:
- [Bug Reports](.github/ISSUE_TEMPLATE/bug_report.yml)
- [Feature Requests](.github/ISSUE_TEMPLATE/feature_request.yml)
- [Questions](.github/ISSUE_TEMPLATE/question.yml)
