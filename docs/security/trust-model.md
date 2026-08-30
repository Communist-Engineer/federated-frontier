# Trust model

The five trust tiers and assets are specified in [trust and identity](../architecture/trust-and-identity.md). This document defines transitions and assurance.

## Principles

Zero trust means authenticate and authorize each workload and artifact, minimize scope and duration, verify integrity, assume breach, and continuously collect evidence. It does not mean equal suspicion or permissionless access to every asset.

Admission evidence may include operator identity, contractual accountability, hardware/software attestation, security review, reproducibility performance, and prior verified work. Each evidence type is stored separately. Tier promotion requires named reviewers and expiry; demotion and emergency fencing are immediate and auditable.

## Control matrix

| Asset/action | T0 | T1 | T2 | T3 | T4 |
|---|---|---|---|---|---|
| Promotion/signing keys | scoped | no | no | no | no |
| Full restricted optimizer state | scoped | allowed | exceptional shard | no | no |
| Restricted datasets | policy role | eligible | scoped/attested | no | no |
| Public/restricted-release model | allowed | allowed | allowed | scoped | public/scoped |
| Authoritative training updates | aggregate | direct + checks | quarantine | experimental only | prohibited |
| Verified trajectories/evals | approve | produce | produce | quarantine | quarantine/checkable |

Independent control planes or partners may federate through mutually authenticated gateways without sharing root authority. Cross-domain artifacts retain original signatures and local policy overlays; federation does not erase sovereignty.
