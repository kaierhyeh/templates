# Playbook: Feature Implementation

Structured development of new capabilities, workflows, or endpoints.

## Phases

### Phase 1: Contract & Precondition Definition
1. Define the exact public interface, data schemas, and edge case behaviors.
2. Identify dependencies and check environmental preconditions.
3. Confirm requirements alignment before implementing large subsystems.

### Phase 2: Behavioral Test Specification
1. Write tests that exercise the desired behavior (inputs, outputs, side effects).
2. Ensure tests run and fail initially due to missing implementation (not syntax errors).

### Phase 3: Incremental Implementation
1. Implement the minimal code required to satisfy the contract.
2. Avoid premature optimization and unnecessary abstractions (YAGNI).
3. Respect existing conventions, idioms, and code styles.

### Phase 4: Integration & Verification
1. Run the full test suite.
2. Test end-to-end integration via CLI or script where applicable.
3. Confirm clean working tree and documentation readiness.
