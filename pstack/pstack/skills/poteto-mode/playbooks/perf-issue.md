# Playbook: Performance Optimization

Data-driven latency, memory, CPU, or throughput optimization.

## Phases

### Phase 1: Establish Baseline Metric
1. Measure baseline latency, CPU, or memory consumption using deterministic benchmarks or timers.
2. Record the exact baseline numbers. Never optimize without a measurable baseline.

### Phase 2: Profile & Identify the Critical Path
1. Use profilers, traces, or timers to isolate the true bottleneck (I/O, database queries, memory allocations, CPU hot loops).
2. Quantify the percentage of total execution time spent in the hotspot.

### Phase 3: Targeted Optimization
1. Apply focused algorithmic or infrastructural optimizations (caching, batching, algorithmic complexity reduction).
2. Avoid micro-optimizations that sacrifice readability for negligible gain.

### Phase 4: Measure Delta & Verify
1. Re-run the benchmark under identical conditions.
2. Report the quantitative improvement (e.g. "Execution time reduced from 450ms to 120ms, a 73% reduction").
3. Verify that all functional and regression tests still pass.
