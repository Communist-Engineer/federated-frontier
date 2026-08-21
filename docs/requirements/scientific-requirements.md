# Scientific requirements

| ID | Requirement | Rationale/source | Priority | Verification | Dependencies | Status |
|---|---|---|---|---|---|---|
| FFI-SCI-001 | Every reported experiment **MUST** carry a complete reproducibility manifest. | Reproducibility is a project output, not an afterthought. | P0 | Independent rerun | FFI-FUNC-008 | Accepted |
| FFI-SCI-002 | Comparisons **MUST** control total training tokens, model architecture, dataset ordering policy, and evaluation budget unless the deviation is the tested variable. | Avoids confounding optimization and compute. | P0 | Protocol review | — | Accepted |
| FFI-SCI-003 | Claims **MUST** distinguish established, supported, plausible, speculative, and unknown status and record E0–E4 evidence. | Prevents projections from becoming facts. | P0 | Evidence review | — | Accepted |
| FFI-SCI-004 | Initial algorithm comparisons **MUST** include centralized, DDP, Local SGD, DiLoCo, an asynchronous variant, branch-train-merge, and one modular/sparse condition. | Directly tests the candidate design space. | P0 | Experiment 0001 report | FFI-SYS-010 | Accepted |
| FFI-SCI-005 | Federation results **MUST** report quality versus wall time, bytes/token, failure exposure, verification overhead, dollars, and energy where measurable. | A loss-only win may be operationally useless. | P0 | Metrics audit | FFI-NFR-002 | Accepted |
| FFI-SCI-006 | A scale transition **MUST** pass a preregistered gate and a review of negative as well as positive results. | Discourages escalation driven by sunk cost or publicity. | P0 | Gate decision record | FFI-SYS-009 | Accepted |
| FFI-SCI-007 | Initial screening at 100M **MUST** use at least three seeds for shortlisted claims; 500M+ confirmations **SHOULD** publish confidence intervals or paired uncertainty. | Small runs are noisy. | P0 | Statistical review | FFI-SCI-004 | Proposed |
| FFI-SCI-008 | Topology and network impairments **MUST** be versioned experimental inputs. | “WAN” is not one condition. | P0 | Manifest validation | FFI-SYS-010 | Accepted |
| FFI-SCI-009 | Negative, null, and failed replication results **SHOULD** remain discoverable. | They are necessary to falsify the thesis and reduce duplicate work. | P1 | Repository audit | — | Proposed |
| FFI-SCI-010 | Vendor benchmark claims **MUST** be labeled as vendor-reported until independently reproduced. | Hardware and system claims often depend on undisclosed conditions. | P0 | Citation audit | — | Accepted |
