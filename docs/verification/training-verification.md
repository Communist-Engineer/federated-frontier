# Training verification

Training verification asks whether an update descends from the assigned checkpoint, data/work budget, and algorithm and whether accepting it is safe. These are separable questions.

## Candidate protocol

1. Issue unpredictable job/seed/canary material after a short-lived lease begins.
2. Require signed environment, parent checkpoint, data-manifest, hyperparameters, token counters, selected intermediate commitments, final delta, and telemetry.
3. Recompute random windows or microbatches on an independent island; compare tolerance-calibrated commitments.
4. Check lineage, staleness, numerical/update bounds, data eligibility, and cross-metric consistency.
5. Evaluate update and composed checkpoint on hidden clean/backdoor suites.
6. Replicate high-influence work; quarantine discrepancies.

TOPLOC-like activation commitments may reduce inference validation cost but require new research for stochastic optimizer trajectories. Proof-of-Learning protocols are not a security boundary because independent attacks show plausible forgery/retraining shortcuts. TEEs can protect a measured code/data path under a vendor trust model, but cannot attest physical energy or exclude all side channels.

Research metrics: detection rate by attack, honest false rejection across hardware, verifier cost/update cost, storage and bandwidth, tolerance drift, collusion resistance, and marginal quality prediction. The fallback is smaller influence and trusted execution, not false certainty.
