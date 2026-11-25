---
name: poteto-mode
description: pstack's master SDLC router. Analyzes the task type, selects the appropriate engineering playbook (bug-fix, feature, refactoring, perf-issue, investigation, prototype, tdd, shipping), enforces verification, and tracks execution checklists.
---

# /poteto-mode: Structured Engineering Workflow Router

When invoked with a task or goal, `/poteto-mode` orchestrates disciplined execution by selecting and running the matching engineering playbook from `playbooks/`.

## 1. Goal Classification

Examine the user request and classify it into exactly one primary playbook:

| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Defect, regression, unexpected crash or error | `playbooks/bug-fix.md` | Reproduce failure $\rightarrow$ Find root mechanism $\rightarrow$ Minimal fix $\rightarrow$ Verify green. |
| New capability, endpoint, workflow, or model | `playbooks/feature.md` | Define contract $\rightarrow$ Write behavioral test $\rightarrow$ Implement $\rightarrow$ Verify integration. |
| Code cleanup, restructuring, deduplication | `playbooks/refactoring.md` | Behavior-preserving transformation: subtract before add, zero regressions. |
| Latency, throughput, memory, or CPU bottleneck | `playbooks/perf-issue.md` | Profile baseline $\rightarrow$ Identify bottleneck $\rightarrow$ Optimize $\rightarrow$ Measure delta. |
| Exploratory research, tracing causal flows | `playbooks/investigation.md` | Read-only analysis. Answer architectural questions with zero file edits. |
| Experimental design forks, throwaway spikes | `playbooks/prototype.md` | Quick isolated probe to resolve technical uncertainty before committing to a design. |
| Strict test-driven requirement | `playbooks/tdd.md` | Red $\rightarrow$ Green $\rightarrow$ Refactor cycle with atomic commits. |
| Final release readiness, PR readiness | `playbooks/shipping.md` | Tree hygiene, full test suite pass, lint clean, changelog verification. |

## 2. Playbook Execution Sequence

1. **Load Playbook**: Read the corresponding file from `playbooks/<type>.md`.
2. **Publish Checklist**: Emit the playbook's phase checklist using `update_steps` or markdown checklist so the candidate sees the explicit trajectory.
3. **Phase Execution**: Follow each phase strictly without skipping steps:
   - Always reproduce / baseline before modifying code.
   - Always keep diffs minimal and reversible.
4. **Mandatory Verification ("Prove It Works")**:
   - Run the compiler, linter, or test runner via `run_command`.
   - Ensure green exit code before declaring the phase complete.
5. **Final Summary**: Hand back the deliverables with the exact verification commands and terminal outputs.
