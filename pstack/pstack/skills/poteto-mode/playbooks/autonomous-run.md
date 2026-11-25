# Playbook: Autonomous Run

Safe, unattended agent loop execution against a strictly checkable exit predicate.

## Phases

### Phase 1: Define Invariant & Exit Predicate
1. Define the exact, checkable exit condition (e.g. `test_suite.py exits with 0`, `all 15 tasks in tasks.json have status "done"`).
2. Set a strict iteration budget (maximum turns or iterations) to prevent infinite loops.
3. Define circuit-breaker criteria: if the same error recurs 3 times consecutively, pause and abort.

### Phase 2: Unattended Execution Loop
1. Execute one atomic chunk of work per turn.
2. Check the exit predicate at the end of each turn.
3. Log state progress into a persistent checkpoint file on disk.

### Phase 3: Post-Run Audit
1. Verify working tree integrity and clean state.
2. Output a summary audit of all mutations performed during the autonomous run.
