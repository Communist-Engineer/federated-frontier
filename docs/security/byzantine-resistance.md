# Byzantine resistance

## Finding

There is no demonstrated method that makes permissionless frontier pretraining updates safe. Krum, coordinate-wise median, trimmed means, clipping, and robust statistics provide value under bounded attacker fractions and distribution assumptions, but heterogeneous/non-IID honest updates can resemble attacks and adaptive backdoors can remain low-norm.

## Defense in depth

1. Limit who may submit weight updates; separate identity, stake/accountability, and reputation.
2. Assign scoped randomized work and require parent/freshness/token lineage.
3. Enforce quotas, norm/coordinate bounds, numerical checks, and robust aggregation candidates.
4. Evaluate deltas and resulting checkpoints on hidden clean, capability, and backdoor suites.
5. Replicate selected work across independent failure/identity domains.
6. Canary, audit, and retain evidence; promote only signed candidates; preserve rollback.
7. Rate-limit influence over time so one accepted update cannot replace the global model.

Robust aggregators are benchmarked against mean/weighted mean on both adversarial and naturally heterogeneous distributions. False rejection of honest specialized islands is a first-class metric.

## Threat campaigns

The test matrix crosses attacker fraction, Sybil concentration, collusion, non-IID data, update staleness, model size, and attack type. Success measures attack success rate, clean quality, detection precision/recall, honest rejection, verification cost, and recovery time.

Tier 4 weight updates remain prohibited. Bonds or stake may provide recourse only after legal/economic analysis and cannot replace technical verification.
