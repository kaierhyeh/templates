# Playbook: Prototype & Spike

Rapid, isolated experimentation to resolve design forks or technical uncertainty.

## Phases

### Phase 1: Frame the Fork
1. Identify the technical uncertainty (e.g. "Can library A meet our latency requirements?").
2. Set a strict time/scope box.

### Phase 2: Build the Spike
1. Write the minimal prototype code in a temporary or branch workspace.
2. Prioritize speed and learning over production hardening.

### Phase 3: Decision & Graduation
1. Evaluate whether the approach works.
2. If validated, document the key learnings and formulate a proper feature plan.
3. Discard the throwaway prototype code rather than merging hacky spike code into main.
