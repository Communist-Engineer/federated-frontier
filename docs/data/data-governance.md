# Data governance

Data governance assigns decision rights over admission, permitted purpose, access, mixture use, retention, deletion, audit, and release. Technical possession does not establish a right to train.

## Roles

- Data steward: documents source, rights, policy, quality, and ongoing obligations.
- Custodian: operates storage and access controls without changing eligibility.
- Experiment owner: proposes a versioned mixture and justifies exceptions.
- Independent reviewer: approves restricted or high-risk use.
- Contributor/rights contact: can dispute attribution or report changed rights.

Partner and restricted data remains in an eligible trust/region boundary; where policy permits, training may move to data instead of copying data outward. Privacy techniques such as aggregation, minimization, confidential computing, or differential privacy are selected for specific threat models; “federated” does not itself provide privacy.

FFI-DATA-007: an eligibility decision **MUST** state purpose, model/release class, geography, trust tier, start/expiry, and reviewer. FFI-DATA-008: revoked material **MUST** be excluded from new assignments and trigger a descendant impact report. FFI-GOV-005: disputed or unknown rights **MUST NOT** be converted into assumed permission by contribution terms.

Open questions include jurisdiction, weight-level deletion, public-record exceptions, collective dataset governance, and compensation. These require legal review and governance decisions, not inference from engineering convenience.
