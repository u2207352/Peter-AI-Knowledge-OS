# Contributing

## Knowledge

Do not edit `raw/` to change history.

Durable knowledge belongs in `wiki/`.

Every important change should include:
- source/evidence
- classification
- confidence
- related Wiki links

## Agent Changes

Keep prompts and scripts deterministic and auditable.

AI-generated Wiki changes should be reviewed before merge.

## Pull Requests

Run:

```bash
python scripts/ai.py lint
```

before opening a PR.
