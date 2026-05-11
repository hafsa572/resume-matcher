# Setup Guide

## Prerequisites

| Tool | Version | Installation |
|------|---------|--------------|
| Python | 3.13+ | [python.org](https://python.org) |
| Node.js | 22+ | [nodejs.org](https://nodejs.org) |
| uv | Latest | [astral.sh/uv](https://docs.astral.sh/uv/getting-started/installation/) |

## Local Development

### Clone Repository

```bash
git clone https://github.com/hafsa572/resume-matcher.git
cd resume-matcher
```

### Backend Setup

```bash
cd apps/backend
cp .env.example .env        # Configure your AI provider
uv sync                      # Install dependencies
uv run uvicorn app.main:app --reload --port 8000
```

### Frontend Setup

```bash
cd apps/frontend
npm install
npm run dev
```

Open **http://localhost:3000** in your browser.

## AI Provider Configuration

Add your provider credentials to `.env`:

```bash
# Ollama (Local - Free)
LLM_PROVIDER=ollama

# OpenAI
LLM_PROVIDER=openai
OPENAI_API_KEY=your_key_here

# Anthropic
LLM_PROVIDER=anthropic
ANTHROPIC_API_KEY=your_key_here

# Google Gemini
LLM_PROVIDER=gemini
GOOGLE_API_KEY=your_key_here
```

## Docker

```bash
docker run --name resume-matcher \
  -p 3000:3000 \
  -v resume-data:/app/backend/data \
  ghcr.io/hafsa572/resume-matcher:latest
```

## Development Commands

### Frontend

```bash
npm run dev      # Start dev server
npm run build    # Build for production
npm run lint     # Check for linting errors
npm run format   # Format with Prettier
```

### Backend

```bash
uv run uvicorn app.main:app --reload --port 8000  # Dev server
uv run pytest                                      # Run tests
```

## Troubleshooting

- **Port 3000 in use**: Change port with `npm run dev -- -p 3001`
- **Python version**: Ensure Python 3.13+ is installed: `python --version`
- **Node version**: Ensure Node 22+ is installed: `node --version`
- **Ollama not connecting**: Check Ollama is running and accessible at the configured URL
