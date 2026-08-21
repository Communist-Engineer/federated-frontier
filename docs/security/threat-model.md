# Threat model

## Assets and security objectives

Assets include unreleased weights and optimizer state, restricted data, signing keys, identities, scheduling authority, artifact registry, evaluation holdouts, verifier secrets, contribution accounts, governance records, research integrity, and service availability. Objectives are confidentiality where promised, model and provenance integrity, auditable attribution, recoverability, and safe release.

## Adversaries

- Faulty or compromised worker returning corrupt, stale, or partial results.
- Dishonest provider exaggerating hardware/work, fabricating rollouts, or replaying artifacts.
- Poisoner/backdoor attacker manipulating data, updates, merges, rewards, or evaluations.
- Sybil/colluding group defeating redundancy, reputation, or robust aggregation.
- Insider abusing promotion, policy, keys, logs, or restricted artifacts.
- External attacker exploiting supply chain, control APIs, island gateway, artifact store, or model service.
- Honest-but-curious operator extracting partner data, prompts, or weights.

## Attack surfaces

Registration and attestation; job and dataset assignment; containers/dependencies; tensor and trajectory transfer; update aggregation; verifier environments; metrics and evaluation; cache/checkpoints; model distribution; accounting; governance and release.

The trust boundary diagram is in [trust and identity](../architecture/trust-and-identity.md). Tier 4 is assumed hostile. Tier 2 is authenticated, not automatically correct. Tier 0 and Tier 1 reduce but do not eliminate insider/supply-chain risk.

## Security cases to test

Sign-flip/scaling and model-replacement updates, rare-trigger backdoors, semantic data poisoning, stale/replayed deltas, forged token counts, colluding redundant workers, evaluator leakage, reward manipulation, checkpoint substitution, malicious containers, identity/key theft, partition-induced split brain, and weight exfiltration.

Residual risk is explicit: general useful training computation cannot currently be cheaply proven; Byzantine-robust aggregation has assumptions that high-dimensional adaptive attackers can violate; once broadly released, weights cannot be recalled.
