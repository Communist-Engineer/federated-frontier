# Data quality and contamination

Quality is multidimensional: correctness, informativeness, diversity, domain coverage, language balance, difficulty, safety, freshness, provenance confidence, and marginal learning value. A single classifier score must not silently determine eligibility.

## Pipeline

1. Exact and near deduplication within and across versions, retaining cluster lineage.
2. Format, language, spam, malware, PII and policy classification with calibrated sampling audits.
3. Benchmark and holdout contamination search using exact, fuzzy, semantic, and provenance-based evidence.
4. Domain-specific quality scoring plus stratified human review.
5. Mixture optimization with caps against source/domain concentration.
6. Post-training influence and memorization audits where feasible.

Contamination reports list benchmark version, matching method, thresholds, review sample, removals, residual risk, and temporal cutoff. Evaluation data is access separated from training assignment and verifier hidden tests.

## Synthetic-data controls

Every synthetic item records generator checkpoint, prompt/template, decoding/tool settings, verifiers, filtering, parents, and iteration. Monitor diversity, self-similarity, error amplification, source-model dominance, and performance on independent human-origin holdouts. Recursive generation pauses when independent quality falls despite synthetic-verifier gains.

FFI-DATA-004: quality filters **MUST** publish calibrated false-positive/negative estimates on stratified samples. FFI-DATA-005: mixture changes **MUST** be versioned experimental variables. FFI-DATA-006: official evaluation sets **MUST NOT** be exposed to general rollout workers when hidden verification is a security control.
