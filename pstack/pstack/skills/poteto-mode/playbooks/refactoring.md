# Playbook: Refactoring

Behavior-preserving code reorganization: cleaner, safer, more maintainable.

## Phases

### Phase 1: Baseline Verification
1. Verify that the existing test suite passes before touching any code.
2. If tests do not exist for the target module, write characterization tests first.

### Phase 2: Identify Smell & Scope Boundary
1. Pinpoint the specific structural issue (dead code, excessive coupling, duplication).
2. Define the invariant: external public behavior, signatures, and contracts must remain 100% identical.

### Phase 3: Subtract Before Adding
1. Delete verified dead code, unused imports, and obsolete helper functions first.
2. Perform transformations in small, atomic, reversible steps.

### Phase 4: Regression Check
1. Re-run tests after every transformation step.
2. Verify git diff is purely structural and contains no accidental behavioral shifts.
