# Playbook: Autopilot Full

End-to-end autonomous implementation cycle from specification to validated delivery.

## Phases

### Phase 1: Spec Analysis & Contract Lock
1. Ingest task requirements and generate a deterministic contract checklist.
2. Verify workspace clean state before beginning.

### Phase 2: Implementation Cycle
1. Execute tasks in sequence: Red (failing test) $\rightarrow$ Green (minimal fix) $\rightarrow$ Refactor.
2. Keep diffs strictly focused; do not touch files outside task scope.

### Phase 3: End-to-End Validation
1. Run full unit, integration, and lint suites.
2. Confirm terminal exit codes and record verification proof.
3. Hand back completed deliverables ready for human review.
