<div align="center">

# Resume Matcher

AI-powered resume tailoring for job applications.

[Website](https://resumematcher.fyi) ✦ [Documentation](https://resumematcher.fyi/docs/installation)

</div>

## Overview

Resume Matcher helps you tailor your resume for each job application using AI. Works locally with Ollama or connect to your favorite LLM provider via API.

## How It Works

1. **Upload** your master resume (PDF or DOCX)
2. **Paste** a job description you're targeting
3. **Review** AI-generated improvements and tailored content
4. **Export** as a professional PDF

## Installation

### Quick Start

```bash
git clone https://github.com/hafsa572/resume-matcher.git
cd resume-matcher
```

**Frontend (Next.js):**
```bash
cd apps/frontend
npm install
npm run dev
```

**Backend (FastAPI):**
```bash
cd apps/backend
uv sync
uv run uvicorn app.main:app --reload --port 8000
```

Open **http://localhost:3000** and configure your AI provider in Settings.

### Supported AI Providers

- **Ollama** - Free, runs on your machine
- **OpenAI** - GPT-5 Nano, GPT-4o
- **Anthropic** - Claude Haiku 4.5
- **Google Gemini** - Gemini 3 Flash
- **OpenRouter** - Access to multiple models
- **DeepSeek** - DeepSeek Chat

### Docker Deployment

```bash
docker run --name resume-matcher \
  -p 3000:3000 \
  -v resume-data:/app/backend/data \
  ghcr.io/hafsa572/resume-matcher:latest
```

- App: http://localhost:3000
- API: http://localhost:3000/api/v1/health
- Docs: http://localhost:3000/docs

## Tech Stack

- **Backend**: FastAPI, Python 3.13+, LiteLLM
- **Frontend**: Next.js 16, React 19, TypeScript
- **Database**: TinyDB (JSON file storage)
- **Styling**: Tailwind CSS 4, Swiss International Style
- **PDF**: Headless Chromium via Playwright

## Development

```bash
# Frontend linting
npm run lint

# Format code with Prettier  
npm run format

# Build
npm run build
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the Apache 2.0 License.
