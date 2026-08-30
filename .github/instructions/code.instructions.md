---
applyTo: "**/*.py,**/*.rs,**/*.go,**/*.ts,**/*.tsx,**/*.cpp,**/*.cu,**/*.sh,**/Dockerfile,**/*.toml,**/*.yaml,**/*.yml"
---

# Code instructions

- Read the approved ExecPlan and governing ADRs before implementation.
- Map behavior to stable requirements and tests.
- Prefer deterministic, observable, restartable components with explicit schemas and bounded resource use.
- Parse external artifacts defensively; authenticate identities and verify hashes and signatures before promotion.
- Add unit, integration, failure-injection, and security tests appropriate to the component.
- Update architecture, requirements, operations, and experiment documentation with behavior changes.
