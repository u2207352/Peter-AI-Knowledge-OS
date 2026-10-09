# Peter Enterprise AI Knowledge OS

Enterprise AI Knowledge Management Architecture built for **Obsidian + ChatGPT**, following the Karpathy LLM Wiki pattern:

**Raw Sources → Wiki → Query → Synthesis → Lint/Audit**

## Domains

- NPI
- Smart Factory
- Operations
- Technology
- Management
- Supplier / Customer
- Meetings
- Reports

## Design Principles

1. `raw/` is immutable source material.
2. `wiki/` is the compiled, linked knowledge layer.
3. ChatGPT acts as research, reasoning, synthesis and knowledge-maintenance engine.
4. Every durable claim should retain evidence/source information.
5. Contradictions and outdated information must be visible.
6. Critical business decisions require human approval.
7. The Vault is designed for desktop and mobile use through Obsidian Sync.
8. Git is recommended for version history and controlled collaboration.

## Quick Start

### Windows PowerShell

```powershell
Set-ExecutionPolicy -Scope Process Bypass
.\scripts\install.ps1
```

### macOS / Linux

```bash
chmod +x scripts/install.sh
./scripts/install.sh
```

The installer creates the Vault in:

```text
~/Obsidian/Peter-AI-Knowledge-OS
```

You can override the location:

```powershell
.\scripts\install.ps1 -VaultPath "D:\Obsidian\Peter-AI-Knowledge-OS"
```

```bash
./scripts/install.sh "$HOME/Obsidian/Peter-AI-Knowledge-OS"
```

## GitHub Template Repository

Recommended repository name:

```text
peter-enterprise-ai-knowledge-os
```

After creating a repository from this template:

```bash
git clone https://github.com/<ORG>/peter-enterprise-ai-knowledge-os.git
cd peter-enterprise-ai-knowledge-os
```

Then run the installer.

## Architecture

```text
Web / Email / Meeting / PDF / ERP / MES
                 |
                 v
              00-Inbox
                 |
                 v
          Raw Source Layer
             /raw/*
                 |
              INGEST
                 |
                 v
              ChatGPT
                 |
                 v
             Wiki Layer
             /wiki/*
                 |
        QUERY / SYNTHESIZE
                 |
                 v
       Decision / Report / SOP
                 |
                 v
              LOG.md
```

## Security

Do not commit:

- customer confidential files
- passwords
- API keys
- tokens
- private credentials
- restricted financial information
- personally identifiable information unless explicitly approved

Use `.gitignore` and keep restricted source material outside the public repository.

## Version

`1.2.0`


## v1.1.0 — AI Agent Layer

The repository now includes a provider-neutral local Agent CLI with an OpenAI Responses API adapter.

Install the optional AI runtime:

```bash
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows PowerShell
# .\.venv\Scripts\Activate.ps1

pip install -r requirements.txt
cp .env.example .env
```

Set `OPENAI_API_KEY` in your environment or `.env`.

### Agent commands

```bash
python scripts/ai.py query "What are the current NPI yield risks?"
python scripts/ai.py ingest 00-Inbox/my-note.md
python scripts/ai.py synthesize "Create an executive summary of Smart Factory AI opportunities"
python scripts/ai.py lint
```

The default workflow is:

```text
Wiki → Raw → AI reasoning → Answer
                  |
                  +--> proposed Wiki update
```

`query`, `ingest`, and `synthesize` do not silently overwrite Wiki knowledge.

To apply an AI-proposed Markdown note:

```bash
python scripts/ai.py ingest 00-Inbox/my-note.md --apply
```

### Web research

Web research is deliberately kept as an explicit step. This prevents the local agent from silently treating unverified internet content as enterprise truth.

Recommended flow:

```text
Web research
   ↓
save source to 00-Inbox/
   ↓
AI ingest
   ↓
Wiki
```

### Multi-device

Use Obsidian Sync for the Vault across desktop/mobile. Keep Git for versioned knowledge governance; do not use Git as a substitute for Obsidian Sync for normal mobile Vault synchronization.

### GitHub Template

GitHub supports marking a repository as a template so users can create a new repository with the same structure and files. After pushing this repository to GitHub, enable:

`Settings → General → Template repository`

Then users can select **Use this template**.


## v1.2.0 — One-click Windows Installer

For Windows, extract the release ZIP and double-click `INSTALL.bat` in the extracted folder. The installer copies the knowledge vault to `%USERPROFILE%\Obsidian\Peter-AI-Knowledge-OS` by default. If a vault already exists, the installer asks before updating it. It does not overwrite the existing vault unless you confirm.

The vault installation does not require Python. The optional AI Agent CLI requires Python and packages from `requirements.txt`; configure your API key separately in `.env` and never share that file.
