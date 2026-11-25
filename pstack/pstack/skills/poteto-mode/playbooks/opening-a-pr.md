# Playbook: Opening a Pull Request

Structured workflow for preparing, formatting, and opening high-signal pull requests.

## Phases

### Phase 1: Pre-Submission Hygiene
1. Run `git status` and `git diff` to ensure zero stray files, debug prints, or untracked test fixtures.
2. Verify all tests pass locally and the branch is rebased cleanly onto the target branch.
3. Keep the diff surgical: ensure high signal-to-noise ratio.

### Phase 2: Contextual PR Description
1. Formulate the PR title following conventional commit guidelines (`feat:`, `fix:`, `refactor:`, `perf:`).
2. Structure the PR body:
   - **Problem / Context**: What was broken or missing, and why does this matter?
   - **Solution**: Concrete technical architecture of the fix or feature.
   - **Verification Proof**: Terminal command outputs, test run logs, or benchmarks proving correctness.
   - **Reversibility**: Migration or rollback instructions if applicable.

### Phase 3: Self-Review
1. Perform a self-review of the diff line by line before handing it over to human reviewers.
2. Check for missing edge-case tests, unintended formatting shifts, and adherence to `ponytail`.
