# Supply-chain security

The federation executes third-party code on valuable accelerators and moves high-value artifacts across administrative boundaries. The supply chain includes source, dependencies, compilers, containers, drivers/firmware, kernels, datasets, models, verifiers, and deployment manifests.

Controls: protected review for promotion logic; pinned lockfiles and hashes; reproducible or attestable builds where feasible; SBOM and vulnerability scanning; signed containers and model/dataset manifests; isolated build and training networks; least-privilege workload identities; read-only inputs and egress controls; secret scanning; dependency update policy; provenance attestations; and emergency revocation.

GPU driver and firmware attestations are useful but vendor/platform-specific. A trusted execution environment narrows some host threats while adding side-channel, availability, and vendor-root risks. Results must state what was measured and what remained outside the trust base.

FFI-SEC-011: production workloads **MUST** resolve images and dependencies by immutable digest. FFI-SEC-012: promotion services **MUST** reject unsigned or policy-ineligible manifests. FFI-SEC-013: verifier images and hidden tests **MUST** be isolated from evaluated contributors. Verification uses tamper, dependency-confusion, and malicious-container exercises.
