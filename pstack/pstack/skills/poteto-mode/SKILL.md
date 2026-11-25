---
name: poteto-mode
description: pstack's master SDLC router. Analyzes the task type, selects the appropriate engineering playbook from all 22 specialized playbooks, enforces verification, and tracks execution checklists.
---

# /poteto-mode: Structured Engineering Workflow Router

When invoked with a task or goal, `/poteto-mode` orchestrates disciplined execution by selecting and running the matching engineering playbook from `playbooks/`.

## 1. Goal Classification (Full 22-Playbook Catalog)

Examine the user request and classify it into exactly one primary playbook from the comprehensive 22-playbook suite:

### Core SDLC & Engineering Playbooks
| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Defect, regression, crash, error | `playbooks/bug-fix.md` | Reproduce failure $\rightarrow$ Find root mechanism $\rightarrow$ Minimal fix $\rightarrow$ Verify green. |
| New capability, endpoint, workflow | `playbooks/feature.md` | Define contract $\rightarrow$ Write behavioral test $\rightarrow$ Implement $\rightarrow$ Verify integration. |
| Code cleanup, restructuring | `playbooks/refactoring.md` | Behavior-preserving transformation: subtract before add, zero regressions. |
| Latency, throughput, memory bottleneck | `playbooks/perf-issue.md` | Profile baseline $\rightarrow$ Identify bottleneck $\rightarrow$ Optimize $\rightarrow$ Measure delta. |
| Exploratory research, tracing causal flows | `playbooks/investigation.md` | Read-only forensic analysis. Answer architectural questions with zero file edits. |
| Experimental design forks, throwaway spikes | `playbooks/prototype.md` | Quick isolated probe to resolve technical uncertainty before committing. |
| Strict test-driven development | `playbooks/tdd.md` | Red $\rightarrow$ Green $\rightarrow$ Refactor cycle with atomic commits. |
| Pre-release readiness, release validation | `playbooks/shipping.md` | Tree hygiene, full test suite pass, lint clean, changelog verification. |

### PR & Collaboration Playbooks
| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Preparing and formatting a pull request | `playbooks/opening-a-pr.md` | Hygiene check, structured description, verification proof, self-review. |
| Managing dependent stacked branches | `playbooks/autopilot-stack.md` | Atomic PR layers, branch chaining, systematic rebase & reconciliation. |
| Monitoring CI/CD and review feedback | `playbooks/babysit.md` | Remote CI triage, conflict resolution, reviewer comment remediation. |

### Autonomous & Session Management Playbooks
| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Unattended long-running execution loop | `playbooks/autonomous-run.md` | Explicit exit predicate, turn budget, circuit breaker, post-run audit. |
| Autonomous implementation cycle | `playbooks/autopilot-full.md` | Spec analysis, test-driven execution cycle, end-to-end verification. |
| Resuming prior session / interrupted work | `playbooks/session-pickup.md` | Trail inspection (git/notes), state reconciliation, zero repeated work. |

### Optimization & Evaluation Playbooks
| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Iterative metric maximization loop | `playbooks/hillclimb.md` | Quantitative benchmark, atomic mutation loop, accept/revert selection. |
| Multi-candidate blind evaluation | `playbooks/eval.md` | Variant framing, parallel execution, blinded judge evaluation matrix. |

### Architecture, Design & Meta Playbooks
| Task Nature | Selected Playbook | Core Objective |
| :--- | :--- | :--- |
| Multi-stage or multi-PR roadmap | `playbooks/multi-phase-plan.md` | Critical path decomposition, milestone contracts, staged execution gates. |
| Parallel agent orchestration | `playbooks/orchestrate.md` | Task partitioning, worker spawning, worktree reconciliation & integration. |
| Pixel-perfect UI verification | `playbooks/visual-parity.md` | Screenshot inspection, layout diffing, multi-breakpoint verification. |
| Design token & spec conformance | `playbooks/design-parity.md` | Semantic tokens, a11y standards, dynamic theme conformance. |
| Adversarial codebase inquiry | `playbooks/interrogate.md` | Uncover implicit assumptions, probe risk surface, architectural hardening. |
| Authoring a new custom agent skill | `playbooks/authoring-a-skill.md` | Procedural guide for authoring, packaging, and validating new skills. |

---

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
