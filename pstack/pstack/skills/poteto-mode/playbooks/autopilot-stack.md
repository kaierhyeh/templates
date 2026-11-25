# Playbook: Autopilot Stack

Managing stacked PRs and dependent branch workflows with clean isolation.

## Phases

### Phase 1: Stack Architecture
1. Deconstruct large features into small, logically atomic PR layers (Layer 1: Schema/Contract $\rightarrow$ Layer 2: Core Logic $\rightarrow$ Layer 3: Endpoints/UI).
2. Ensure each layer is independently buildable, testable, and reviewable.

### Phase 2: Branch Chaining
1. Branch each sequential layer from its predecessor (`feature-part-2` from `feature-part-1`).
2. Clearly annotate the stack hierarchy in the PR description header (`Stack: #1 -> #2 -> #3`).

### Phase 3: Stack Rebase & Reconciliation
1. When changes are requested on a lower layer, amend the lower layer commit.
2. Rebase dependent layers systematically: `git rebase --onto <new-base> <old-base> <child-branch>`.
3. Verify test suites pass across all branches in the stack after rebasing.
