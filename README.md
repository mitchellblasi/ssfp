# SSFP

SSFP is a story-driven AI software factory template that helps teams define work in `work.json`, execute implementation with quality and security gates, and capture outcomes in `results.json`.

## Adoption

Point your local AGENTS.md to this repo url and tell your agent to adopt this pattern.

*NOTE* Please validate the contents of the repo and agents file before you run this prompt

## Contents

- `AGENTS.md`: operating policy with explicit contracts, gates, and status transitions.
- `schemas/work.schema.json`: JSON Schema for `work.json`.
- `schemas/results.schema.json`: JSON Schema for `results.json`.

## Usage

### Example Prompt: Generate Work

```text
Create a new story in work.json for password reset by email.
```

### Example Prompt: Execute Work

```text
Execute all pending stories in work.json.
```
