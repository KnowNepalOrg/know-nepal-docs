# Architecture Decisions

## Overview

This section records significant architectural decisions made during
the development of Know Nepal.

The purpose of these records is to preserve the reasoning behind
important technical decisions and provide context for future
contributors.

---

## Architecture Decision Records

| ADR | Decision |
|---|---|
| [ADR-001: Modular Monolith](ADR-001-modular-monolith.md) | Use a modular monolith as the current backend architecture |

---

## When to Create an ADR

An Architecture Decision Record should be considered when a decision:

- Has a significant impact on the system architecture.
- Affects multiple parts of the project.
- Introduces or removes an important technology or infrastructure
  component.
- Changes an established architectural direction.
- Would benefit future contributors who need to understand why the
  decision was made.

Small implementation choices do not require an ADR.

---

## ADR Principles

Architecture decisions should:

- Clearly describe the problem being addressed.
- Explain the considered options.
- Record the chosen approach.
- Document the reasoning behind the decision.
- Describe important consequences.
- Reflect the state of the project at the time of the decision.

ADRs document decisions and their reasoning; they do not replace the
current architecture documentation.

---

## Decision Status

An ADR may be:

- **Accepted** — The decision is currently in effect.
- **Superseded** — A later decision has replaced it.
- **Deprecated** — The decision is no longer relevant to the project.

---

## Related Documentation

- [ADR-001: Modular Monolith](ADR-001-modular-monolith.md)
- [Architecture Overview](../architecture/overview.md)
- [Backend Architecture](../architecture/backend.md)
