# AI Software Factory Policy

## Objective
Execute user stories from `work.json` safely and reproducibly, with measurable quality and security outcomes recorded in `results.json`.

## Security Rules Source
All story execution must follow `rules/security-rules.md`.

## Story Contract
Each story must contain:

- `id`: unique stable key (e.g., `SSFP-001`)
- `title`
- `description`
- `acceptance_criteria`: non-empty list
- `security_requirements`: non-empty list
- `status`: `todo|in_progress|blocked|done`

## Execution Rules
- Process stories in dependency-safe order.
- A story can move to `in_progress` only from `todo`.
- `done` is allowed only when acceptance criteria and definition of done are all satisfied.
- Add or update tests for all newly introduced behavior.
- Map each story to applicable rules in `rules/security-rules.md` before implementation.
- Verify and document rule compliance for all new or modified behavior.
- Run security checks on all new or modified code.
- If security findings are found, ask the user if they would like them to be fixed.
- If blocked, set `status=blocked` and include blocker details in `results.json`.

## Quality Gates (required)
- JSON schema validation for `work.json` and `results.json`
- Static checks: lint and type checks
- Unit tests pass
- Coverage threshold met (recommended: 85% minimum)
- Security checks pass for code and dependencies

## Results Contract
For each executed story, append a result object with:

- `id`
- `status`: `done|blocked|failed`
- `unit_tests`: list of command/result strings
- `quality_gates`: list of command/result strings
- `security_review`: findings and disposition

`security_review` must include:
- which `rules/security-rules.md` rule IDs were applied
- verification evidence for each applied rule
- any failed or waived rule and rationale

## Stop Conditions
Stop and request clarification when:

- Story requirements conflict.
- Required secrets/access are missing.
- Safety or compliance requirements cannot be met.
