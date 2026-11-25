# Playbook: Authoring a Skill

Standardized procedure for authoring, packaging, and testing new agent skills.

## Phases

### Phase 1: Define Intent & Scope
1. Define what procedure the skill teaches the agent, its trigger keywords, and completion conditions.
2. Ensure the skill solves a reusable workflow rather than a one-off ad-hoc script.

### Phase 2: Draft SKILL.md
1. Write clean YAML frontmatter (`name`, `description`).
2. Structure procedural steps with clear imperatives, guardrails, and input/output contracts.
3. Keep descriptions concise to minimize system prompt context budget overhead.

### Phase 3: Validation & Testing
1. Validate directory layout: `skills/<name>/SKILL.md`.
2. Run skill validation via `agy plugin validate` or test invocation.
3. Verify that the agent adheres to the skill's instructions during execution.
