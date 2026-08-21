# Federated data architecture

The data system treats a dataset as a signed graph of immutable content, transformations, policy, and usage—not a path to a mutable bucket.

Sources include public-domain and open corpora, licensed and partner data, contributor submissions, simulations, synthetic data, tool traces, and verified trajectories. Ingestion isolates bytes; scanning classifies license, PII, malware, language/domain, policy, and quality; deduplication and contamination checks occur before eligibility. A dataset version is a manifest referencing content-addressed shards and parent manifests.

FFI-DATA-001: every training-eligible record or auditable batch **MUST** resolve to content hash, source, license/policy, collection date, creator/contributor, transformations, generated status/model, quality, language/domain, contamination and PII status, eligibility, usage, and parent/derived artifacts. Where per-record storage is prohibitive, batch metadata must include a defensible mapping and exception rationale.

## Storage tiers

- Quarantine: untrusted/raw, tightly scoped access, scanners and legal review.
- Curated: normalized and deduplicated, not necessarily training eligible.
- Eligible: approved for named purposes, jurisdictions, model/release classes, and expiry.
- Derived: tokenized shards, mixtures, synthetic outputs, trajectories, and evaluation sets.
- Revoked/tombstoned: excluded from new runs with affected descendants discoverable.

Object bytes may live in multiple stores; the registry remains authoritative for identity and policy. Regional caches enforce the same grants and cannot silently promote local additions.

Adopt interoperable mappings to W3C PROV-O for lineage, Croissant for dataset discovery/structure, SPDX 3.0 AI/Dataset profiles for license and software-bill-of-material relationships, and CycloneDX ML-BOM where consumers require it. No single standard covers the full training provenance graph.
