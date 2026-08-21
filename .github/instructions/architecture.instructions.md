---
applyTo: "docs/architecture/**/*.md,docs/adr/**/*.md,ARCHITECTURE.md"
---

# Architecture instructions

- Start from requirements and quantified physical constraints.
- Compare alternatives and state consequences across compute, network, quality, reliability, security, economics, and governance.
- Keep high-frequency collectives inside a compute island unless an experiment explicitly tests a wider boundary.
- Treat external inputs as hostile and show trust boundaries.
- Use ADR statuses Proposed, Accepted, Rejected, Superseded, or Experimental.
