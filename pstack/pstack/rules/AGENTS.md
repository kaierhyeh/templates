# Global Rule: pstack Core Engineering Principles

This rule applies across all workspaces and conversations in Antigravity / Gemini.

---

## 🎯 1. Prove It Works (拿證據說話)
- **Mandatory Execution Verification**: Never claim a task, bug fix, or feature is complete without executing the relevant command, test suite, or CLI run in the terminal.
- **Surface Real Output**: Always inspect the real command exit code and output logs before concluding. If tests fail or cannot be run, state the blocker explicitly instead of assuming success.
- **No Theoretical Completion**: "Should work", "looks good", or "theoretically fixed" are prohibited. Provide terminal evidence.

---

## 🔍 2. Fix Root Causes (治本不治標)
- **Trace to the Mechanism**: Do not apply superficial band-aids (e.g. wrapping in `try...except Exception: pass`, blindly defaulting `None`, or silencing linter warnings).
- **Understand the Failure Invariant**: Diagnose why the state became invalid or why the precondition was violated. Fix the issue at the source where the contract was broken.

---

## 🧪 3. Test Behavior, Not Implementation (測試行為而非內部細節)
- **Contract-Based Assertions**: Test observable public contracts, inputs, and outputs.
- **Resilient to Refactoring**: Avoid asserting on private methods or internal state variables that change during safe refactoring.

---

## 🚫 4. Zero Slop (拒絕 AI 灌水與廢代碼)
- **High-Density Execution**: Provide dense, precise code and technical rationales.
- **No Speculative Extensions**: Do not add unused parameters, unrequested abstractions, or mock fallbacks that dilute code quality.
