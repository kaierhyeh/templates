# Playbook: Interrogate

Deep adversarial questioning and audit of implicit codebase assumptions.

## Phases

### Phase 1: Identify Invariants & Assumptions
1. Inspect the codebase for implicit assumptions (e.g. "user IDs are always sequential", "requests never timeout", "clock skew is zero").
2. Catalog unhandled edge cases, hidden state mutations, and unvalidated inputs.

### Phase 2: Probe the Risk Surface
1. Formulate probing questions: "What happens if this network call fails halfway through?", "What if this queue fills up?"
2. Write edge-case test probes to stress-test the suspected vulnerabilities.

### Phase 3: Hardening Recommendations
1. Document confirmed failure vectors with precise code references.
2. Propose concrete architectural guardrails and contract fortifications.
