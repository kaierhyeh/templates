# Playbook: Session Pickup

Restoring operational state and context from a prior agent trail without repeating work.

## Phases

### Phase 1: Trail Inspection
1. Read git status, recent commit history (`git log -n 5`), and modified uncommitted files.
2. Read the latest conversation notes, task lists, or scratch files to identify where the previous turn stopped.

### Phase 2: State Reconciliation
1. Verify which checklist items were truly completed (check tests or file existence).
2. Mark completed steps as `done`; do not re-execute passing tests or already-implemented code blocks.

### Phase 3: Resume Execution
1. Resume directly from the first incomplete step.
2. Output a brief 2-sentence pickup confirmation to the user stating the detected state and next action.
