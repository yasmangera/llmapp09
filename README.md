# LLMSecOps workshop: llmapp09

This repository is my copy of the [workshop starter project](https://github.com/darryl1975/llmapp09). It contains the multi-model backend, Flask frontend, Docker Compose setup, Promptfoo and DeepEval suites, and four GitHub Actions workflows.

## What I configured

- Updated the backend and frontend image workflows to use my Docker Hub namespace.
- Excluded local environments, caches, and `.env` files from Docker build contexts.
- Added Git and Ruff configuration so local secrets stay untracked and the existing code passes lint.

## Local verification (12 October 2026)

- Both Docker images built successfully.
- The Compose application ran with a local Ollama instance. The frontend returned HTTP 200, the backend returned its model routes, and a classification request returned a structured response.
- Backend unit tests: **72 passed**.
- Ruff checks: **passed** for both backend and frontend.

The local smoke test used installed Ollama models. The GitHub evaluation workflows require valid hosted Ollama settings, and the DeepEval workflow also requires an OpenAI API key.

## GitHub Actions secrets

Configure these under **Settings > Secrets and variables > Actions**:

- `DOCKERHUB_TOKEN`
- `OLLAMA_API_KEY`
- `OLLAMA_BASE_URL`
- `OPENAI_API_KEY`

Do not commit credentials or `.env` files.
