# Proof of useful computation

## Feasibility classification

| Method | What it supports | Current classification | Limits |
|---|---|---|---|
| Deterministic program verifier | Output correctness for code/proofs/simulators | Production-feasible now | Does not prove resources used; verifier coverage matters |
| Redundant execution + hidden canaries | Statistical confidence and fraud detection | Production-feasible now | Multiplies cost; collusion/Sybils |
| Challenge-response/spot checks | Selected intermediate work | Production-feasible in narrow jobs | Work may be selectively honest |
| TEE/remote attestation | Measured software/platform start | Production-feasible with platform limits | Not proof of learning; side channels/vendor roots |
| TOPLOC-like commitments | Empirical inference consistency | Research prototype (E1–E2) | Hardware/numerical assumptions, inference focus |
| Proof of Learning | Claimed training trace | Research prototype with published attacks | Retraining/forgery and storage burden |
| zkML/SNARK/STARK inference | Cryptographic statement of execution | Prototype; high-value narrow use | Large proving latency/cost |
| General verifiable frontier training | Complete honest training | Theoretical/unknown | Prohibitive trace and proof complexity |

## Policy

Pay or credit for accepted useful output, not unverifiable effort. Randomized assignment, hidden tasks, redundant identities, quality evaluation, lineage, and delayed settlement make fabrication less profitable. Verifiers are independently versioned and audited.

For gradient work, prefer trusted/authenticated islands plus bounded influence and post-update evaluation. Do not describe hash submission, uptime, or hardware attestation as proof of training.
