# Training packet schema

One unit of work is one task or skill + one skill version + one learner + one environment.

Training ID: `<skill-id>@<version>:<learner-id>:<environment-id>`

A Codex recording with multiple tasks creates multiple packets.

## Required fields

```yaml
schema_version: "1.0"
training_id: truecoach-exercise-lookup@1.0:ara:grok-computer
source:
  codex_recording_reference: ""
  event_stream_reference: ""
  source_digest: ""
  direct_observations: []
  inferences: []
task:
  skill_id: truecoach-exercise-lookup
  version: "1.0"
  goal: ""
  trigger: ""
  inputs: []
  outputs: []
  in_scope: []
  out_of_scope: []
  decision_points: []
  expected_observables: []
target:
  learner_id: ara
  learner_name: Ara
  environment_id: grok-computer
  trainer_id: truecoach
  config_reference: agents/ara/config.example.toml
lesson:
  procedure: []
  safe_fixture_references: []
  critical_checks: []
  prohibited_effects: []
  remediation_rules: []
training:
  state: INVENTORY
  attempt_cap: 4
  consecutive_passes: 0
  attempts: []
  corrections: []
  evidence_references: []
result:
  status: NOT_RUN
  verified_by: ""
  unresolved_issues: []
report:
  group_id: ""
  message_id: ""
  permalink: ""
curation:
  ssot_reference: ""
  classification: ""
  repository_path: ""
  commit_or_pull_request: ""
  hindsight_bank_id: source
  retain_receipt: ""
  recall_receipt: ""
data_handling:
  approved_clinical_source_reference: ""
  public_reusable_summary: ""
```

## Status values

`NOT_RUN`, `BLOCKED:INPUT`, `BLOCKED:ENV`, `BLOCKED:AUTHORITY`, `BLOCKED:AUTH`, `BLOCKED:HUMAN_AUTH`, `BLOCKED:UNSAFE`, `NEEDS_REVIEW:ATTEMPT_CAP`, `NEEDS_REVIEW:RUBRIC_CONFLICT`, `NEEDS_REVIEW:CANON_CONFLICT`, `PARTIAL:REPORT`, `PARTIAL:CURATION`, `VERIFIED`, `ARA_VERIFIED_MVP`, `PROVISIONAL`
