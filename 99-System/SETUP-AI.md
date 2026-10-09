# AI Runtime Setup

The optional local Agent CLI uses the official OpenAI Python library and the Responses API.

## Install

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Credentials

Create `.env` from `.env.example`:

```text
OPENAI_API_KEY=...
OPENAI_MODEL=gpt-5.5
```

Never commit `.env`.

## Commands

```bash
python scripts/ai.py lint
python scripts/ai.py query "What are the top NPI risks?"
python scripts/ai.py ingest 00-Inbox/example.md
python scripts/ai.py ingest 00-Inbox/example.md --apply
python scripts/ai.py synthesize "Build an executive summary of Smart Factory AI opportunities"
```

The agent intentionally uses a dry-run default for knowledge writes.

## Web Research

For current information, use an explicit Web research step and save the source into `00-Inbox/` before ingestion. This preserves provenance and prevents accidental blending of stale Wiki information with current external claims.
