# Verification plane

The verification plane turns untrusted proposals into evidence-bearing candidates. Its operating maxim is: **models propose; programs verify; the federation aggregates**.

## Assurance ladder

1. Schema, hash, lineage, and policy validation.
2. Deterministic machine verifier where available.
3. Hidden/canary tasks and statistical anomaly checks.
4. Redundant execution across independent identities and failure domains.
5. Empirical activation commitments or spot checks for inference.
6. Attested execution for stronger stack identity.
7. Cryptographic proof for narrow high-value workloads when affordable.

No single rung is universal. Proof-of-learning research has known attacks; attestation does not prove learning; zkML is far from cost-free. The system records which rung supported each acceptance.

## Promotion rule

Verification produces a signed decision referencing artifact, checks, verifier versions, identities, conflicts, confidence, and policy. Failed work is quarantined with reason; contradictory verifier results trigger escalation. Verification services themselves are replicated, versioned, monitored for drift, and prevented from evaluating their own training artifacts when feasible.

## Contribution value

For contributor `i`:

\[
U_i=C_i\,Q_i\,V_i\,R_i\,P_i,
\]

where `C` is normalized compute/output volume, `Q` measured marginal quality, `V` verification confidence, `R` reliability, and `P` policy eligibility. A zero policy or verification term means no useful credit even if raw compute was expended.
