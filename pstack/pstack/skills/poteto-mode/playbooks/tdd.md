# Playbook: Test-Driven Development (TDD)

Strict Red-Green-Refactor development cycle.

## Phases

### Phase 1: Red (Failing Test)
1. Write a focused unit or integration test describing the desired behavior.
2. Run the test and verify that it fails for the expected reason (assertion failure, not syntax error).

### Phase 2: Green (Minimal Implementation)
1. Write the simplest possible code to make the test pass.
2. Run the test again and verify it turns green.

### Phase 3: Refactor (Clean Up)
1. Clean up duplicated logic, improve naming, ensure compliance with `ponytail`.
2. Keep tests green after every modification.
