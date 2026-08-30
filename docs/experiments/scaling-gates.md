# Empirical scaling gates

Thresholds below are initial decision rules for the next experiment, not universal constants. Each stage preregisters tighter values based on prior measurement.

## Gate G0 — documentation and laboratory readiness

- Reproducibility/provenance manifest validates at 100% required fields.
- Network shaping reproduces target profiles within ±10% bandwidth and ±5 ms or ±10% latency, whichever is larger.
- Baseline can resume from a corrupted/lost worker without promoting corrupt state.
- Threat-model and access tests pass; no Tier 4 path reaches training secrets.

## Gate G1 — low-communication result (100M–500M)

- Validation-loss gap ≤1% relative to the token-matched best centralized/DDP baseline, plus no material downstream regression.
- Transmitted WAN bytes/token improve ≥10× over cross-island DDP.
- Time-to-quality ≤1.25× the best feasible baseline under the same WAN profile.
- Partition recovery completes within two configured outer periods with no lineage ambiguity.
- Result repeats across at least three seeds at 100M and confirms on a preselected 500M condition.

## Gate G2 — 1B two-island result

Repeat G1 with sustained runs, real geographic link, heterogeneous scheduling, energy/cost accounting, and adversarial update tests. At least one independent operator reproduces the manifest.

## Higher gates

G3 (3–7B) requires multiple geographic operators and a safe async/quorum result. G4 (20–40B or Track A RL) requires verifier, rollout, and release controls. G5 (100B+ sparse) requires local MoE efficiency and hierarchical router evidence. G6 frontier attempt requires demonstrated advantage over centralized alternatives, mature incident/security governance, funding, and an independent scientific review.

Any provenance, dangerous-capability, model-security, or governance veto blocks scaling even when quality/cost pass. A failed gate produces a result and revised hypothesis, not an invitation to spend more compute.
