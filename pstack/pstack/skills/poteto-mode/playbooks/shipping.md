# Playbook: Shipping & Release Readiness

Pre-release validation and hygiene checklist before landing code.

## Phases

### Phase 1: Working Tree Hygiene
1. Run `git status` and `git diff` to confirm zero unintended files or temporary artifacts.
2. Verify all modified files are formatted and clean.

### Phase 2: Comprehensive Test Suite
1. Run the entire project test suite, not just local unit tests.
2. Verify all tests pass with zero warnings or errors.

### Phase 3: Documentation & Changelog
1. Verify README, documentation, and interface specs match the new reality.
2. Summarize changes clearly for peers or release notes.
