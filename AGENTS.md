# Agent operating contract

## Mission

Build an evidence-led, reproducible program for testing whether frontier intelligence can be trained, improved, served, verified, and governed through a federation of independently operated compute. Treat every architectural claim as a hypothesis until evidence and an ADR establish otherwise.

## Source of truth

Use this precedence order:

1. accepted ADRs in `docs/adr/`;
2. normative requirements in `docs/requirements/`;
3. architecture specifications in `docs/architecture/`;
4. active execution plans in `docs/exec-plans/active/`;
5. research synthesis and evidence in `docs/research/`;
6. root summaries and tool-specific adapters.

When sources conflict, record the conflict and repair the higher-level traceability chain. Tool-specific instructions adapt this contract; they never create a separate project truth.

## Required reading by task

- Research: `RESEARCH.md`, `docs/research/evidence-matrix.md`, and `docs/research/bibliography.md`.
- Architecture: `ARCHITECTURE.md`, relevant requirements, candidate architectures, and ADRs.
- Experiment: `docs/experiments/methodology.md`, `metrics.md`, `scaling-gates.md`, and the experiment specification.
- Security or trust: `SECURITY.md`, `docs/security/threat-model.md`, and `docs/architecture/trust-and-identity.md`.
- Governance or licensing: `GOVERNANCE.md` and `docs/governance/`.
- Implementation: the approved active ExecPlan plus every requirement and ADR it cites.

## Research rules

- Prefer original papers, official technical reports, repositories, standards, and vendor specifications.
- Record publication date, experimental scale, topology, hardware, network conditions, limitations, and replication status.
- Classify every material claim E0–E4 using `docs/research/evidence-matrix.md`.
- Distinguish established, supported, plausible, speculative, and unknown statements.
- Label vendor-reported results and preserve uncertainty. Add sources to the bibliography and evidence matrix in the same change.
- Search for disconfirming evidence and failure modes before recommending an architecture.

## Change workflow

1. Inspect relevant evidence, requirements, ADRs, and active ExecPlans.
2. For complex work, create or update an ExecPlan using `docs/exec-plans/README.md`.
3. Add or revise stable requirement IDs before implementing behavior.
4. Create an ADR for decisions with durable architectural consequences. Insufficiently supported decisions remain `Proposed` or `Experimental`.
5. Implement the smallest change that tests the stated hypothesis.
6. Run applicable validation and record exact commands, environment, and results.
7. Update architecture, traceability, experiment records, security analysis, and operational documentation together.

## Validation contract

The repository is documentation-first today. Until code-specific commands are accepted in an ADR, validate:

- Markdown links and anchors;
- Mermaid parsing where tooling is available;
- duplicate requirement and ADR identifiers;
- evidence-to-requirement-to-ADR-to-experiment traceability;
- unresolved placeholders and unsupported quantitative claims;
- changed-file review for secrets, credentials, personal data, and restricted datasets.

Never invent a successful command, benchmark, replication, citation, or security property. Record unavailable validation as an explicit gap.

## Security boundaries

- Treat external workers, updates, datasets, trajectories, and model artifacts as hostile inputs.
- Keep Tier 0 credentials, signing keys, unrestricted checkpoints, restricted data, and release controls outside contributor workloads.
- Require content hashes, signatures, provenance, policy decisions, and immutable audit events for promoted artifacts.
- Use synthetic fixtures in examples. Never commit secrets, production endpoints, personal data, or licensed data samples.
- Follow responsible disclosure in `SECURITY.md`.

## Pull requests

Each PR should state the hypothesis or requirement changed, evidence added, ADR impact, validation performed, security implications, and unresolved questions. Keep research claims reviewable and citations close to the claims they support.

## Nested instructions

Introduce a nested `AGENTS.md` only when a subtree gains distinct build, safety, data, or validation rules. Keep it short and scoped; deeper instructions override this file only within their directory tree.
