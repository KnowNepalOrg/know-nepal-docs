# Roadmap

## Overview

The Know Nepal roadmap describes the general direction of the project
and the areas that are expected to evolve over time.

The roadmap is intentionally high-level. Specific implementation
details, priorities, and timelines may change as development progresses.

---

## Current Focus

Current development is focused on strengthening the existing platform
and improving its reliability.

Key areas include:

- Expanding and refining domain functionality.
- Improving backend security and authorization.
- Increasing test coverage and integration validation.
- Improving the AI-assisted trip-planning experience.
- Maintaining and improving the frontend experience.
- Improving deployment and infrastructure reliability.
- Keeping technical documentation aligned with the implementation.

---

## Near-Term Direction

The project is expected to continue improving the existing architecture
rather than introducing unnecessary infrastructure complexity.

Areas of focus include:

### Platform

- Continue developing the existing domain modules.
- Improve consistency across domain functionality.
- Refine shared backend capabilities where appropriate.

### Security

- Continue strengthening authentication and authorization.
- Ensure protected operations are enforced by the backend.
- Improve security testing and validation.

### Testing

- Expand unit and integration testing.
- Improve validation of API behavior.
- Strengthen testing around security-sensitive functionality.

### AI Trip Planning

- Continue improving personalized trip planning.
- Improve the use of Know Nepal's destination and itinerary data.
- Refine the overall trip-planning experience.

### Infrastructure

- Improve deployment reliability.
- Continue refining project infrastructure and CI/CD.
- Keep operational complexity appropriate for the project's current
  scale.

### Documentation

- Keep public documentation synchronized with the actual system.
- Document significant architectural decisions.
- Expand documentation as new capabilities are introduced.

---

## Long-Term Direction

As Know Nepal grows, the architecture may evolve in response to actual
technical and operational requirements.

Potential future areas include:

- Additional domain functionality.
- More advanced personalization.
- Improved data quality and coverage.
- Greater system scalability.
- Additional infrastructure and operational capabilities.
- Extraction of individual domains into independent services if there
  is a clear technical reason to do so.

These are directional possibilities rather than committed
implementation plans.

---

## Architectural Evolution

The current architecture is a modular monolith.

Future architectural changes should be driven by measurable technical
requirements such as:

- Scaling requirements
- Domain ownership
- Deployment independence
- Operational isolation
- Performance requirements
- Infrastructure needs

The project should avoid introducing distributed architecture solely
for the sake of adopting microservices.

---

## Roadmap Principles

The roadmap follows these principles:

- Prioritize real user and engineering needs.
- Improve the existing platform before adding unnecessary complexity.
- Prefer incremental improvements.
- Keep security and reliability as ongoing priorities.
- Validate architectural changes before adopting them.
- Update the roadmap as project priorities change.

---

## Status

The roadmap is not a fixed schedule.

Priorities may change based on development progress, technical
requirements, available resources, and project goals.

The current implementation remains the source of truth for what has
actually been completed.

---

## Related Documentation

- [Current State](current-state.md)
- [Architecture Overview](../architecture/overview.md)
- [Architecture Decisions](../decisions/README.md)
- [Development Workflow](../contributing/workflow.md)
