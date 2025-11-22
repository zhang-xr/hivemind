# Repository Guidelines

## Project Structure & Module Organization
- `src/hivemind/`: core package (`BaseAgent`, `LLMClient`, `HistoryStrategy`, shared types).
- `src/hivemind/core/`: orchestration utilities (`AgentConfig`, builders, assistants).
- `src/hivemind/tools/`: reusable `ExecutableTool` implementations and `FlexibleContext`.
- `config.ini.template`: sample model/provider config; copy to `config.ini` and fill keys (do not commit secrets).

## Setup, Build & Development Commands
- Create a virtualenv and install deps:
  - `python -m venv .venv && source .venv/bin/activate`
  - `pip install -r requirements.txt`
- Run a quick LLM connectivity check (from repo root):
  - `PYTHONPATH=src python -m hivemind.llmclient`
- There is no dedicated build step; this is a pure Python library.

## Coding Style & Naming Conventions
- Python 3.9+ with PEP 8: 4-space indents, max 120-char lines, UTF-8 files.
- Use `snake_case` for functions/variables, `PascalCase` for classes, and `UPPER_SNAKE_CASE` for constants.
- Prefer type hints and docstrings for public APIs; keep logging and printouts concise and helpful.

## Testing Guidelines
- Currently no formal test suite. When adding tests, use `pytest` under `tests/` with files named `test_*.py`.
- Example: `PYTHONPATH=src pytest -q`.
- Include focused unit tests for new agents, tools, and configuration behavior.

## Commit & Pull Request Guidelines
- Write clear, concise commit messages; optional prefixes like `feat:`, `fix:`, `chore:` are welcome.
- For each PR, include: purpose, key changes, any new config options, and testing performed.
- Link related issues when available and add screenshots or logs only when they clarify behavior.

## Security & Configuration Tips
- Never commit real API keys or sensitive URLs. Use `config.ini.template` as the public baseline.
- Prefer environment variables (`OPENAI_API_KEY`, `DEEPSEEK_API_KEY`, etc.) over hard-coded secrets.

