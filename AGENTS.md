# AGENTS.md — Enterprise AI Knowledge OS

## Mission

Maintain a persistent enterprise knowledge wiki for NPI and Smart Factory operations.

The AI must improve the knowledge base over time instead of producing isolated answers.

## Core Model

```text
RAW SOURCES
    ↓
INGEST
    ↓
WIKI
    ↓
QUERY
    ↓
SYNTHESIZE
    ↓
DECISION / OUTPUT
    ↓
AUDIT / LINT
```

## Non-Negotiable Rules

1. Never silently modify `raw/`.
2. Never present an AI inference as a verified fact.
3. Preserve source/evidence information for important claims.
4. Search existing Wiki knowledge before starting external research.
5. Use Web research when current information is required.
6. When new information changes existing knowledge, update the relevant Wiki note.
7. Do not overwrite historical decisions; record changes.
8. Detect and document contradictions.
9. Prefer one canonical Wiki note per concept/entity/process.
10. Use `[[Wiki Links]]` to connect related knowledge.
11. Keep notes understandable without relying on hidden AI context.
12. Critical business, legal, customs, financial and customer decisions require human approval.

## Operations

### INGEST

Convert raw material into structured knowledge.

Input:
- meeting notes
- emails
- PDFs
- spreadsheets
- web research
- supplier/customer documents

Output:
- atomic Wiki notes
- source links
- tags
- properties
- relationships

### QUERY

Answer from:

1. existing Wiki
2. relevant raw source
3. Web research if needed

Always distinguish:
- verified fact
- sourced interpretation
- AI inference
- open question

### SYNTHESIZE

Combine multiple Wiki notes into:
- executive summary
- NPI action plan
- SOP
- management report
- roadmap
- decision memo

### LINT

Check:
- missing source
- broken links
- duplicate concepts
- stale notes
- contradictions
- missing properties
- unsupported claims

## Evidence Levels

| Level | Meaning |
|---|---|
| A | Official / primary source |
| B | Customer or supplier official document |
| C | Professional research / consulting |
| D | Industry source |
| E | AI inference |
| F | Hypothesis |

## Security Classification

Use:

- `public`
- `internal`
- `confidential`
- `restricted`

## Naming

Prefer:

```text
YYYY-MM-DD-topic.md
```

for raw/event notes.

Prefer:

```text
concept-name.md
process-name.md
problem-name.md
solution-name.md
```

for durable Wiki knowledge.

## Human Approval

The AI must not autonomously approve:
- customer commitments
- customs/legal conclusions
- financial decisions
- supplier commitments
- production release decisions
- quality disposition
- security-sensitive actions
