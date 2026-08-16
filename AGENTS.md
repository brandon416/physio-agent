# AGENTS.md — physio-agent

Shared rules for every Hermes learner. Environment overlays live under `agents/<name>/`. Do not add `agents/<name>/AGENTS.md` until a verified environment-specific instruction exists.

## Identities

| Role | ID | Name |
| --- | --- | --- |
| Orchestrator | captain | Captain |
| Trainer | truecoach | TrueCoach |
| Learner | ara | Ara |
| Canon owner | source-keeper | Source Keeper |
| Later learner | mia | Mia (NOT_RUN) |
| Later learner | wanda | Wanda (NOT_RUN) |

Stable keys: `learner_id`, `environment_id`, `trainer_id`. Do not key work by machine nicknames alone.

## State machine

INVENTORY -> ARCHITECTURE_READY -> PACKET_ACCEPTED -> TRUECOACH_LEARNING -> TRUECOACH_READY -> ARA_TRAINING -> ARA_VERIFIED_MVP or BLOCKED/NEEDS_REVIEW -> REPORTED -> CURATED -> DONE

Training ID: `<skill-id>@<version>:<learner-id>:<environment-id>`

Example: `truecoach-exercise-lookup@1.0:ara:grok-computer`

## Authority

- Live TrueCoach writes need `confirm=true`. Training confidence does not grant write authority.
- TrueCoach MCP for reads, previews, and final read-back. CLI for dry-runs and authorized writes.
- No browser, Chrome, Playwright, Computer Use, or improvised API for TrueCoach.
- If the operation is not on MCP or CLI, stop and report `TRUECOACH_MCP_CLI_CAPABILITY_UNAVAILABLE`.
- Ara does not self-certify mastery or authorize promotion.
- TrueCoach does not independently certify its own teaching as successful.
- Captain uses an isolated verifier for the final rubric.

## Readiness

- `PROVISIONAL`: guided run or one unguided pass
- `ARA_VERIFIED_MVP`: two consecutive unguided passes on distinct safe fixtures, every critical check passed, no unauthorized effects
- `VALIDATED_99`: later measured evaluation set. Do not report a self-rated 99%

## Config precedence

1. `config/shared.example.toml`
2. `agents/<name>/config.example.toml`
3. Ignored machine-local `.env`

Committed files use semantic names, repository-relative paths, and `${ENV_VAR}` references only.

## Artifact lanes

- `APPROVED_CLINICAL`: stays in approved clinical owner systems
- `PUBLIC_REUSABLE`: this repository. No raw patient records, tokens, passwords, or absolute home paths

## Canon

- SSOT/SOP and Hindsight bank `source` (Canon) are owned by Source Keeper
- `physio-agent` is versioned agent material
- `True-Coach Training` is operational reporting
- Raw recordings are source evidence, not canon

## Promotion

Source Keeper classifies each element as `SHARED_INVARIANT`, `ENVIRONMENT_OVERLAY`, or `UNRESOLVED_CONFLICT`. Do not overwrite unresolved conflicts. A skill proven only on Ara is `verified_on: ara`.
