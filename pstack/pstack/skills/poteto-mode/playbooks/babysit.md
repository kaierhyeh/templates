# Playbook: Babysit

Active monitoring, CI/CD triage, and review feedback loop management.

## Phases

### Phase 1: CI Pipeline Monitoring
1. Monitor remote build and CI/CD pipelines after pushing commits.
2. If CI fails, pull remote logs immediately to inspect failure traces.

### Phase 2: Conflict & Flake Triage
1. Differentiate between true regressions and flaky/environmental test failures.
2. If merge conflicts arise against the main branch, rebase locally, resolve conflicts surgically, and re-run local tests before re-pushing.

### Phase 3: Review Comment Remediation
1. Address reviewer feedback atomically: one commit per distinct concern or discussion thread.
2. Verify fixes locally with terminal evidence and post concise response notes directly addressing the reviewer's points.
