# Playbook: Investigation

Read-only exploratory inquiry into system causality, architecture, or edge cases.

## Phases

### Phase 1: Frame the Inquiry
1. Define the specific question to answer (e.g. "How does component X handle race conditions during Y?").
2. State the investigative boundaries and relevant source modules.

### Phase 2: Evidence Gathering (Read-Only)
1. Read relevant source files, configuration manifests, and logs.
2. Trace the data flow and execution path step by step.
3. Strictly prohibit modifying, creating, or deleting code during an investigation.

### Phase 3: Synthesis & Findings
1. Formulate the factual conclusion supported by citations to exact code lines.
2. Provide actionable recommendations or risk assessments.
