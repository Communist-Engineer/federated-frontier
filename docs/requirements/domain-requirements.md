# Domain requirements

This register consolidates training, network, RL, inference, verification, data, governance, and interface requirements defined in domain specifications. The domain documents provide full rationale.

| ID | Normative statement | Priority | Verification | Status |
|---|---|---|---|---|
| FFI-TRAIN-001 | High-frequency tensor, pipeline, context, and expert collectives **MUST** remain within a measured low-latency island by default. | P0 | Topology tests | Proposed |
| FFI-TRAIN-002 | Each island update **MUST** bind parent, token weight, algorithm/precision, lineage, metrics, and signature. | P0 | Update contract | Proposed |
| FFI-TRAIN-003 | External updates **MUST** pass freshness, bounds, quota, numerical, lineage, and evaluation quarantine before aggregation. | P0 | Adversarial suite | Proposed |
| FFI-TRAIN-004 | Outer optimizer and aggregation state **MUST** be checkpointed and recoverable with global weights. | P0 | Restore equivalence | Proposed |
| FFI-TRAIN-005 | Async aggregation **MUST** record staleness, quorum, grace-window, and token weighting for every applied update. | P0 | Async trace audit | Experimental |
| FFI-TRAIN-006 | Branch/module merging **MUST** declare compatibility, parentage, method, evaluation, and optimizer-state treatment. | P1 | Merge report | Experimental |
| FFI-NET-001 | Training results **MUST** report transmitted bytes/token and compute/communication/idle/recovery time. | P0 | Metrics audit | Accepted |
| FFI-NET-002 | Default WAN-critical paths **MUST NOT** require per-token round trips. | P0 | Architecture test | Accepted |
| FFI-NET-003 | The lab **MUST** inject and validate asymmetric bandwidth, latency, jitter, loss, and partitions. | P0 | Network calibration | Accepted |
| FFI-NET-004 | Protocols **MUST** be correct under retry, duplication, reordering where applicable, and reconnection. | P0 | Fault/property tests | Proposed |
| FFI-RL-001 | Policy training, rollout, environments, verification, evaluation, replay, and distribution **MUST** be independently schedulable. | P0 | Workflow test | Proposed |
| FFI-RL-002 | A trajectory **MUST** bind policy/environment versions, episode identity, sampling, rewards, verifier evidence, lineage, and hash. | P0 | Contract test | Proposed |
| FFI-RL-003 | Policy lag **MUST** be measured; rejection or off-policy correction **MUST** be explicit and tested. | P0 | Staleness experiment | Proposed |
| FFI-RL-004 | Permissionless trajectories **MUST** be quarantined, deduplicated, and checkable/reproducible/discardable. | P0 | Fraud campaign | Accepted |
| FFI-RL-005 | Hidden evaluators and reward systems **MUST** be separated from contributors when leakage enables gaming. | P0 | Access test | Proposed |
| FFI-RL-006 | Contribution accounting **MUST** use accepted verified value, not raw sampled tokens alone. | P1 | Accounting audit | Proposed |
| FFI-INF-001 | Request routing **MUST** consider model placement, cache locality, capacity, latency, trust/privacy, cost, and failure. | P0 | Routing replay | Proposed |
| FFI-INF-002 | WAN tensor/expert splitting **MUST NOT** be a production default. | P0 | Placement test | Accepted |
| FFI-INF-003 | Inference workers **MUST** advertise versioned model/kernel/context/quantization and queue capabilities. | P0 | Registration test | Proposed |
| FFI-INF-004 | Requests **MUST** carry deadline, privacy class, idempotency/retry, and compatible fallback policy. | P0 | Failure tests | Proposed |
| FFI-INF-005 | Privacy-classed routes **MUST** enforce data-region/trust/logging policy. | P0 | Policy tests | Proposed |
| FFI-INF-006 | Serving reports **MUST** include TTFT, inter-token latency, tail latency, useful throughput, cache hits, errors, and energy where measurable. | P1 | SLO audit | Proposed |
| FFI-INF-007 | Long-running agent work **SHOULD** expose signed resumable application state. | P1 | Resume test | Proposed |
| FFI-VERIFY-001 | Tier 4 work **MUST** be machine-checkable, independently reproducible, or safely discardable. | P0 | Admission tests | Accepted |
| FFI-VERIFY-002 | Acceptance **MUST** name verification mode, evidence, verifier version, and confidence. | P0 | Decision audit | Proposed |
| FFI-VERIFY-003 | Numerical tolerances **MUST** be calibrated across permitted hardware/software. | P0 | Cross-hardware study | Proposed |
| FFI-VERIFY-004 | Replayed/identical work **MUST** be deduplicated and excluded from independent agreement. | P0 | Replay attack test | Proposed |
| FFI-VERIFY-005 | Verifier changes **MUST** pass regression and adversarial exploit testing. | P0 | Verifier CI | Proposed |
| FFI-VERIFY-006 | Reward models **MUST NOT** be the sole verifier for high-impact permissionless work. | P0 | Architecture review | Accepted |
| FFI-DATA-001 | Training-eligible data **MUST** carry the provenance and policy fields in the data architecture. | P0 | Manifest audit | Proposed |
| FFI-DATA-002 | Runs **MUST** bind an immutable mixture and actual consumption record. | P0 | Replay audit | Proposed |
| FFI-DATA-003 | Policy changes **MUST** support forward exclusion and descendant impact query. | P0 | Revocation drill | Proposed |
| FFI-DATA-004 | Quality filters **MUST** publish calibrated error estimates on stratified samples. | P1 | Sampling audit | Proposed |
| FFI-DATA-005 | Mixture changes **MUST** be versioned experimental variables. | P0 | Run manifest | Accepted |
| FFI-DATA-006 | Hidden official evaluations **MUST NOT** be exposed where secrecy is an integrity control. | P0 | Access test | Proposed |
| FFI-DATA-007 | Eligibility **MUST** state purpose, release class, geography, tier, expiry, and reviewer. | P0 | Policy audit | Proposed |
| FFI-DATA-008 | Revoked data **MUST** be excluded from new jobs and produce a descendant impact report. | P0 | Revocation drill | Proposed |
| FFI-GOV-001 | Governance **MUST** name decision and appeal rights for model, data, compute, release, budget, and incidents. | P0 | Charter review | Proposed |
| FFI-GOV-002 | Material governance decisions **MUST** be auditable and evidence-linked. | P0 | Decision audit | Proposed |
| FFI-GOV-003 | Contribution terms **MUST** state compensation, attribution, IP, access, voice, and dispute process before work. | P0 | Onboarding test | Proposed |
| FFI-GOV-004 | Weight release **MUST** identify authority, evidence, dissent, and irreversible-risk rationale. | P0 | Release review | Proposed |
| FFI-GOV-005 | Unknown/disputed data rights **MUST NOT** be converted into assumed permission. | P0 | Data audit | Accepted |
| FFI-IFACE-001 | Federation interfaces **MUST** be versioned and compatible over a declared window. | P0 | Compatibility CI | Proposed |
