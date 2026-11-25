# Playbook: Bug Fix

Disciplined defect remediation: reproduce, root-cause, minimal fix, prove with evidence.

## Phases

### Phase 1: Reproduce & Isolate
1. Construct the minimal reproduction command, script, or unit test.
2. Run it and capture the exact failure trace and error message.
3. If reproduction is flaky, stabilize the test environment before proceeding.

### Phase 2: Root-Cause Analysis
1. Trace the execution call stack back to the invalid state transition or broken invariant.
2. Formulate a causal hypothesis: "Component X failed because precondition Y was violated when input Z occurred."
3. Do not apply superficial band-aids (null-checks, catch-all wrappers).

### Phase 3: Minimal Surgical Fix
1. Apply the smallest necessary change that directly resolves the root cause.
2. Adhere to `minimal-diff-reversibility`: touch only the necessary lines.
3. Ensure no unrelated formatting or refactoring is intermingled.

### Phase 4: Prove It Works
1. Run the reproduction test/command again. Verify it now passes cleanly.
2. Run the surrounding regression test suite to confirm zero collateral breakage.
3. Capture terminal exit code and test output.
