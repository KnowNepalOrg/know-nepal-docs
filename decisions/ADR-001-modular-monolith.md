# ADR-001: Modular Monolith

- **Status:** Accepted
- **Date:** 2026
- **Decision:** Use a modular monolith for the Know Nepal backend

## Context

Know Nepal contains multiple domain areas, including:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare

The project previously explored a microservices-based architecture,
where these areas could be developed and deployed as independent
services.

However, independently deploying and operating multiple services
introduces additional infrastructure, deployment, networking, and
operational complexity.

For the current stage of the project, that additional complexity is
not justified.

---

## Decision

Know Nepal uses a **modular monolith** as its current backend
architecture.

The domain areas are implemented as separate modules within a single
Spring Boot application.

Each domain maintains clear application and persistence boundaries while
sharing common backend infrastructure.

The current backend therefore provides domain separation without
requiring each domain to be independently deployed.

---

## Why This Approach

The modular monolith provides a balance between domain separation and
operational simplicity.

It allows the project to:

- Maintain clear domain boundaries.
- Keep domain responsibilities separated.
- Reduce deployment complexity.
- Reduce infrastructure requirements.
- Simplify local development.
- Avoid unnecessary service-to-service communication.
- Keep the system easier to operate at the current project stage.

---

## Alternatives Considered

### Microservices

A microservices architecture was previously explored.

Under this approach, individual domains could operate as independently
deployed services.

While this provides stronger deployment and runtime isolation, it also
introduces additional complexity around:

- Service deployment
- Networking
- Service communication
- Configuration
- Monitoring
- Infrastructure management
- Operational overhead

This complexity is not currently necessary for Know Nepal.

**Decision:** Not selected as the current architecture.

---

### Single Application Without Domain Boundaries

Another option would be to build the backend as a single application
without explicit domain separation.

This would simplify the initial structure but would make it harder to
maintain clear ownership and boundaries between different areas of the
platform.

**Decision:** Not selected.

---

## Consequences

### Benefits

The decision provides:

- Lower operational complexity.
- Lower infrastructure requirements.
- Simpler deployment.
- Simpler development and testing.
- Clear separation between domain areas.
- A structure that can evolve as the project grows.

### Trade-offs

The modular monolith means:

- All backend modules are deployed together.
- A failure in the application can potentially affect multiple domains.
- Independent scaling of individual domains is not available.
- Strong module boundaries must be maintained through development
  practices.

These trade-offs are accepted for the current stage of the project.

---

## Future Evolution

The modular monolith is not intended to prevent future architectural
changes.

If a domain eventually requires independent deployment, scaling,
ownership, or operational isolation, it can be evaluated for extraction
into an independent service.

Such a change should be driven by a clear technical or operational
requirement rather than adopting distributed architecture prematurely.

---

## Related Documentation

- [Architecture Overview](../architecture/overview.md)
- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
- [System Context](../architecture/system-context.md)
