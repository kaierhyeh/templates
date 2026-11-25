# Playbook: Orchestration & Parallel Delegation

Fanning out complex tasks across parallel agents and reconciling worktrees safely.

## Phases

### Phase 1: Task Partitioning
1. Partition the problem into mutually exclusive, independent work units (e.g. separate modules, independent microservices, decoupled test files).
2. Explicitly specify the inputs, interfaces, and expected file outputs for each parallel worker.

### Phase 2: Agent Spawning & Monitoring
1. Delegate work units using `invoke_subagent` or `/swarm` with task-specific briefs.
2. Ensure subagents operate within their defined boundaries without cross-modifying shared files.

### Phase 3: Reconciliation & Integration
1. Collect artifacts and outputs from all workers.
2. Merge worktrees or apply patches sequentially.
3. Run the integrated test suite to verify no subtle inter-worker regressions or contract violations.
