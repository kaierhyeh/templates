# Playbook: Multi-Phase Plan

Architecting multi-stage or multi-PR roadmaps for complex engineering initiatives.

## Phases

### Phase 1: Decomposition & Critical Path
1. Break down the overarching objective into distinct, sequential milestones.
2. Map out the dependency graph: identify the critical path and tasks that can run concurrently.

### Phase 2: Milestone Contract Definition
1. For each phase, specify:
   - **Prerequisites**: What must be green before this phase starts.
   - **Deliverables**: Code files, schemas, endpoints, or tests produced.
   - **Verification Gate**: Deterministic test/command verifying phase completion.

### Phase 3: Staged Execution & Checkpoints
1. Execute phase by phase. Never start Phase N+1 until Phase N has passed its verification gate.
2. Keep progress checkpointed so interruptions can be resumed smoothly via `session-pickup`.
