# Machine-verifiable environments

| Domain | Proposal | Verifier/evidence | Principal residual risk |
|---|---|---|---|
| Software | patch, program, exploit/fix | unit/integration tests, compiler, fuzzing, static analysis, reproducible build | weak/hidden tests, sandbox escape, benchmark leakage |
| Formal mathematics | proof term | Lean, Isabelle/HOL, Rocq/Coq kernel | wrong formalization, library/version dependence |
| Symbolic reasoning | assignment/proof | SAT/SMT certificate, symbolic algebra | encoding mismatch, solver bugs |
| Circuits | netlist/layout | SPICE and rule/constraint checks | simulator fidelity and objective gaming |
| Engineering | geometry/controller/design | CAD constraints, FEM/CFD, numerical certificates | discretization/model error |
| Agents | trajectory/tool result | environment state, tests, transaction receipt | reward hacking, state leakage |

Environments are content-addressed, containerized, resource limited, network isolated by default, and versioned with hidden/public tests separated. Results bind simulator/verifier version, inputs, seeds, tolerances, outputs, and certificate. Reproducible computation validates the specified environment, not necessarily reality; scientific tasks require uncertainty and external validation.

FFI-VERIFY-001: Tier 4 work **MUST** be machine-checkable, independently reproducible, or safely discardable. FFI-VERIFY-005: verifier changes **MUST** trigger regression and exploit testing. FFI-VERIFY-006: reward models **MUST NOT** be the sole verifier for high-impact permissionless contributions.
