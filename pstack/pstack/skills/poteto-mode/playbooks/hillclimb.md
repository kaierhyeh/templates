# Playbook: Hillclimbing

Iterative loop pattern for maximizing a target metric, benchmark score, or optimization goal.

## Phases

### Phase 1: Metric & Benchmark Definition
1. Define the objective function or quantitative benchmark (e.g. latency score, accuracy %, throughput req/s).
2. Establish a baseline score by running the benchmark on the unoptimized system.

### Phase 2: Mutation & Trial Loop
1. Hypothesize a specific targeted improvement.
2. Apply the single atomic change to code or parameters.
3. Run the evaluation benchmark under identical conditions.

### Phase 3: Selection & Graduation
1. If metric improves: accept the mutation as the new baseline.
2. If metric degrades or stagnates: reject mutation and roll back cleanly via `git checkout`.
3. Repeat until metric plateaus or target threshold is reached.
