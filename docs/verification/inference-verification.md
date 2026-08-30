# Inference and rollout verification

Inference is more verifiable than full training because the function and inputs can be bounded. Exact re-execution is complicated by nondeterministic kernels and sampling, so protocols declare acceptable numerical and probabilistic equivalence.

## Modes

- Deterministic verifier: rerun deterministic decoding or check a final program/proof/simulator certificate.
- Selective replay: independently recompute hidden prompts/tokens or randomly selected segments.
- Commit then challenge: worker commits outputs/intermediate summaries before sample indices are revealed.
- Redundancy: compare independent workers, weighted by identity and correlated-failure analysis.
- Attested inference: measured stack plus signed output, with explicit platform trust.
- Cryptographic proof: SNARK/STARK/zkML for small or high-value circuits when latency permits.

Rollout sampling records RNG and decoding configuration; a worker cannot choose only favorable episodes after seeing rewards. Deduplication detects replay across assignments. Hidden canaries measure execution honesty, while semantic/output verifiers measure usefulness.

FFI-VERIFY-002: acceptance **MUST** name the verification mode and confidence. FFI-VERIFY-003: verifier tolerances **MUST** be calibrated across permitted hardware. FFI-VERIFY-004: identical/replayed work **MUST** be excluded from independent-redundancy counts.
