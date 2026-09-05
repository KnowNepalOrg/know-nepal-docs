# Testing

## Overview

Testing is used to verify the correctness and reliability of Know Nepal
as the platform evolves.

The project uses multiple levels of testing to validate application
logic, API behavior, persistence, and integration between components.

The exact test configuration and commands are defined in the respective
source repositories.

---

## Testing Layers

Know Nepal uses testing at different levels depending on the behavior
being verified.

### Unit Tests

Unit tests verify individual components in isolation.

They are primarily used to test:

- Business logic
- Service behavior
- Validation
- Utility functions
- Individual application components

Unit tests should remain focused and avoid unnecessary dependencies on
external systems.

---

### Integration Tests

Integration tests verify that multiple application components work
together correctly.

They may be used to validate interactions between:

- Controllers and services
- Services and repositories
- Application components and databases
- Security and authenticated requests

Integration tests are useful when behavior cannot be reliably verified
through isolated unit tests.

---

### API Tests

API-level tests verify the behavior of REST endpoints.

They can validate:

- Request handling
- Response status codes
- Request and response data
- Validation behavior
- Authentication and authorization
- Error responses

API tests help ensure that the backend contract behaves as expected
for frontend consumers.

---

### Database Testing

Database-related tests verify persistence behavior and interactions
with PostgreSQL.

Where integration testing requires a real database environment, the
test environment should use isolated test databases or test
infrastructure rather than development or production databases.

---

## Test Organization

Tests should remain close to the code and responsibility they verify.

Backend tests should follow the structure of the backend application,
while frontend tests should follow the structure and tooling of the
frontend application.

The source repositories remain the source of truth for the exact test
directory structure.

---

## Testcontainers

Some backend integration tests may use **Testcontainers** to provide
isolated infrastructure during testing.

When Testcontainers-based tests are used, Docker must be available in
the development environment.

Tests that require external infrastructure should be clearly
distinguished from tests that can run without it.

---

## Testing Principles

The project follows these general testing principles:

- Test important application behavior rather than implementation
  details.
- Keep unit tests focused and isolated.
- Use integration tests where component interaction matters.
- Verify API contracts through API-level tests.
- Keep test data isolated from development and production data.
- Include security behavior in tests for protected operations.
- Avoid unnecessary or duplicate tests.
- Keep tests maintainable as the application evolves.

---

## Before Submitting Changes

Before submitting a change, developers should:

1. Run the relevant tests for the modified component.
2. Run broader tests when the change affects shared functionality.
3. Verify that new behavior has appropriate test coverage.
4. Check that existing tests continue to pass.
5. Ensure tests do not depend on production credentials or data.

The exact commands for running the test suites should be taken from
the corresponding source repository.

---

## Related Documentation

- [Development Setup](setup.md)
- [Repository Structure](repository-structure.md)
- [Conventions](conventions.md)
- [Backend Architecture](../architecture/backend.md)
- [Security Overview](../security/overview.md)
