# Know Nepal Documentation

Project-wide documentation for **Know Nepal**.

Know Nepal is an open-source project focused on building a structured digital platform for discovering, organizing, and accessing information about Nepal.

This repository contains documentation about the project itself, including its purpose, ecosystem, development practices, contribution process, and shared concepts.

## Documentation

### Project

* [Introduction](project/introduction.md) — Purpose, scope, principles, and background of Know Nepal.
* [Ecosystem](project/ecosystem.md) — Overview of the repositories and major components that make up Know Nepal.
* [Roadmap](project/roadmap.md) — Current direction and future development plans.

### Development

* [Getting Started](development/getting-started.md) — Guide for developers setting up the Know Nepal project locally.
* [Contribution Guide](development/contribution-guide.md) — How to contribute code, documentation, issues, and improvements.

### Reference

* [Glossary](reference/glossary.md) — Definitions of terminology used throughout the project.

## Documentation Boundaries

This repository focuses on **project-wide documentation**.

Technical infrastructure, deployment, and infrastructure architecture are maintained separately in the [`know-nepal-infrastructure`](https://github.com/KnowNepalOrg/know-nepal-infrastructure) repository.

This separation helps keep documentation organized and prevents different repositories from becoming competing sources of truth.

## Project Architecture

Know Nepal currently uses a **modular monolithic backend architecture**.

Domain areas such as:

* Geography
* History
* Culture
* Destinations
* Wildlife
* Education
* Healthcare

are organized as modules within the backend rather than being independently deployed services.

The project architecture may evolve as the platform grows. Documentation should always reflect the current implementation rather than an outdated or planned architecture.

For detailed technical architecture and infrastructure documentation, see the [Know Nepal Infrastructure](https://github.com/KnowNepalOrg/know-nepal-infrastructure) repository.

## Documentation Principles

Know Nepal documentation should be:

* **Clear** — Easy to understand without unnecessary complexity.
* **Accurate** — Reflect the actual state of the project.
* **Simple** — Avoid unnecessary duplication and bureaucracy.
* **Useful** — Answer practical questions for developers and contributors.
* **Maintainable** — Easy to update as the project evolves.
* **Consistent** — Use common terminology across the project.

## Contributing

Documentation improvements are welcome.

If you find information that is incorrect, outdated, incomplete, or difficult to understand, please open an issue or submit a pull request.

When making documentation changes:

1. Keep changes focused and understandable.
2. Verify information against the current project.
3. Avoid duplicating documentation maintained in another repository.
4. Update related documentation when a change affects it.

## Related Repositories

Know Nepal is organized across multiple repositories, each with a specific responsibility.

For an overview of the project ecosystem and repository responsibilities, see the [Ecosystem](project/ecosystem.md) documentation.

## License

This repository is licensed under the [MIT License](LICENSE).
