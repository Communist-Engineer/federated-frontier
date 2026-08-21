# Federation benchmark and metrics

## Training and quality

| Metric | Definition/reporting rule |
|---|---|
| Validation loss/perplexity | Fixed held-out manifest, token-weighted; report uncertainty |
| Time-to-quality | Wall time to preregistered loss/score, including recovery and verification |
| Tokens/s | Non-padding trained tokens over end-to-end wall time |
| MFU | Achieved model FLOPs / declared theoretical peak; publish FLOP convention |
| Accelerator utilization | Kernel-active and memory/idle distributions, not a single mean |
| Downstream capability | Versioned suites with contamination/saturation controls |

## Communication and federation

- Logical and transmitted bytes per step, synchronization, trained token, and accepted useful artifact.
- Compute, communication, collective wait, idle/straggler, verification, and recovery time.
- Join/admission latency, churn tolerance, completed work before expiry, staleness distribution.
- Recovery point objective, recovery time, lost/repeated tokens, checkpoint corruption detection.
- Quality and throughput by hardware/topology class; concentration by provider and region.

## Security and verification

Attack success rate, clean-quality degradation, detector precision/recall, honest false rejection, collusion tolerance, canary detection, redundant agreement, proof/attestation overhead, verifier latency and cost, time to containment, rollback success, and residual unverified influence.

## Economics and energy

Report compute, egress/network, storage, verification, failure/rework, coordination, and engineering separately. Metrics include dollars/trained token, dollars/time-to-quality, dollars/quality-point, accepted useful contribution/dollar, joules or watt-hours/token where measured, and uncertainty/sensitivity to price and utilization.

## Intelligence evaluation

Use a changing portfolio spanning language, coding, mathematics, science, multimodality, long context, tool use, calibrated reasoning, safety, and autonomous task completion. “Frontier” is a rolling percentile/reference set defined in [definitions](../vision/definitions.md), not a permanent benchmark score.
