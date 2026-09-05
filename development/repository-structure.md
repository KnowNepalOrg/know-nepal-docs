# Repository Structure

## Overview

Know Nepal is organized across multiple repositories, with each
repository having a specific responsibility within the project.

The repositories are separated by concern so that application code,
documentation, infrastructure, and project-level development can be
managed independently.

---

## Repository Responsibilities

The main repositories are organized around the following responsibilities:

| Repository | Responsibility |
|---|---|
| `know-nepal-platform` | Core application platform and backend development |
| `know-nepal-api` | Public API-related development |
| `know-nepal-docs` | Project-wide technical documentation |
| `know-nepal-infrastructure` | Infrastructure and deployment configuration |

Additional repositories may exist for specific project components or
experiments.

The exact repository configuration and implementation remain defined by
the corresponding source repositories.

---

## Platform Repository

`know-nepal-platform` contains the core Know Nepal application
platform.

The backend is implemented as a Spring Boot modular monolith, with
domain modules for:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare

The platform repository is the primary source for backend application
implementation.

---

## API Repository

`know-nepal-api` contains API-related project code and resources.

API behavior, endpoint implementations, request and response models,
and related configuration should be documented according to the current
state of the repository.

---

## Documentation Repository

`know-nepal-docs` contains public technical documentation for the Know
Nepal project.

It documents:

- Project scope
- Architecture
- Domains
- Data architecture
- API concepts
- Development practices
- Deployment
- Security
- Architectural decisions
- AI-related architecture and behavior

The documentation repository does not replace the source code.

---

## Infrastructure Repository

`know-nepal-infrastructure` contains infrastructure and deployment
configuration for the project.

It is responsible for project-level operational concerns such as:

- Deployment configuration
- Infrastructure definitions
- Environment-related configuration
- Networking
- CI/CD configuration

Sensitive credentials and secrets must not be stored in the public
documentation repository.

---

## Source of Truth

Each repository remains the source of truth for the implementation it
owns.

Documentation should describe the current behavior and architecture
without duplicating implementation details unnecessarily.

When documentation and implementation differ, the relevant source
repository should be checked and the documentation updated accordingly.

---

## Repository Boundaries

Repositories should maintain clear responsibilities.

Application code should remain in the appropriate application
repository, infrastructure configuration should remain in the
infrastructure repository, and project-wide documentation should remain
in the documentation repository.

This separation keeps the project easier to maintain as Know Nepal
continues to evolve.

---

## Related Documentation

- [Development Setup](setup.md)
- [Testing](testing.md)
- [Conventions](conventions.md)
- [Architecture Overview](../architecture/overview.md)
