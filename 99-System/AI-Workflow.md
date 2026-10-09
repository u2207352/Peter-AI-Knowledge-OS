# AI Workflow

## 1. Capture

```text
Web / Email / Meeting / PDF / Spreadsheet
                ↓
             00-Inbox
```

## 2. Ingest

ChatGPT:
- identify entities
- identify concepts
- identify problems
- extract evidence
- detect relationships
- create or update canonical Wiki notes

## 3. Query

Priority:

```text
Wiki → Raw → Web
```

Use Web when the question requires current information.

## 4. Synthesize

Create:
- action plan
- report
- SOP
- roadmap
- decision memo

## 5. Audit

Check:
- sources
- evidence
- freshness
- contradictions
- links
- duplicate notes

## Recommended ChatGPT Prompt

```text
You are the Enterprise Knowledge Agent.

Follow AGENTS.md and Knowledge-Schema.md.

First inspect the existing Wiki knowledge.
Do not modify raw sources.
Separate verified facts from inference.
If current information is required, perform Web research.
When new durable knowledge is discovered, propose the exact Wiki note(s)
that should be created or updated.

Return:
1. Answer
2. Evidence
3. Existing Wiki notes used
4. New knowledge discovered
5. Contradictions / open questions
6. Recommended Wiki updates
```
