# Security policy

## Scope

Security covers repository software, control-plane designs, model and dataset artifacts, worker protocols, contribution verification, identity, signing, release controls, and the research infrastructure described here.

## Reporting

Use GitHub private vulnerability reporting when enabled. Otherwise contact the repository owner through a private channel listed on the owner profile. Include affected component, preconditions, impact, reproduction at the minimum safe level, and suggested mitigation. Public issues suit general hardening ideas after sensitive details are removed.

## Baseline rules

- External artifacts enter quarantine and receive hashes, provenance, malware/content scanning, policy evaluation, and signature verification before promotion.
- Tier 0 secrets, signing keys, unrestricted frontier checkpoints, and restricted datasets stay outside participant jobs.
- Workers receive least-privilege, short-lived identities and artifact capabilities.
- Security events are append-only, time-synchronized, and attributable to authenticated principals.
- Capability and release gates scale with model risk; see `docs/security/model-security.md`.

Design detail lives in the [threat model](docs/security/threat-model.md), [trust model](docs/security/trust-model.md), and [Byzantine analysis](docs/security/byzantine-resistance.md).
