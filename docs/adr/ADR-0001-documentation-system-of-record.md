# ADR-0001 — Documentation as the system of record

- Status: Accepted
- Date: 2026-08-21
- Owners: Project maintainers
- Requirements: FFI-SYS-007, FFI-SCI-001, FFI-SYS-009

## Context and evidence

Researchers, humans, Copilot, Codex, Grok, and future agents need one auditable project truth. Copying full rules into tool-specific files creates divergence.

## Decision

`docs/` is authoritative for research, requirements, architecture, experiments, governance, and ADRs. Root documents summarize and navigate. `AGENTS.md` is the common operating contract; tool-specific instructions adapt it without forking project truth. Implementation changes update linked documents in the same change.

## Alternatives

Wiki-only documentation was rejected because it is not commit-coupled. Tool-specific encyclopedias were rejected because precedence and synchronization fail. Code-only truth is inapplicable in the research phase.

## Consequences and validation

Changes are more reviewable but carry documentation maintenance cost. Link, requirement, ADR, and citation audits validate the decision. Revisit if documentation cannot remain connected to executable validation.
