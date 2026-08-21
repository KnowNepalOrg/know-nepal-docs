# Know Nepal Documentation

> Public documentation for **Know Nepal** — a structured digital knowledge platform focused on Nepal.

Know Nepal is being developed to make useful, structured information about Nepal easier to **discover, understand, maintain, and eventually contribute to**.

The platform currently covers several knowledge domains:

* 🗺️ Geography
* 📜 History
* 🎭 Culture
* 🏔️ Destinations
* 🐅 Wildlife
* 🎓 Education
* 🏥 Healthcare

This repository contains the public documentation for the project.

---

## 📖 About This Documentation

The purpose of this repository is to provide a clear and maintainable place for people to understand Know Nepal without having to study the entire source codebase first.

The documentation covers areas such as:

* Project overview
* Architecture
* Domain structure
* Data and database concepts
* API information
* Development
* Testing
* Deployment
* Security
* Contribution guidelines
* Architectural decisions

The documentation describes **the project as it currently exists**.

Planned or proposed functionality will be clearly identified rather than presented as implemented.

---

## 🏗️ Current Architecture

Know Nepal currently uses a **modular monolith architecture**.

The backend is organized around independent domain modules while running as a single application.

```text
                    Know Nepal
                        │
              ┌─────────┴─────────┐
              │                   │
          Frontend             Backend
              │                   │
              │          Modular Monolith
              │                   │
              │      ┌────────────┼────────────┐
              │      │            │            │
              │  Geography     History      Culture
              │  Destinations  Wildlife     Education
              │  Healthcare
              │                   │
              │              PostgreSQL
              │
              └────── HTTP / REST ──────┘
```

The architecture may evolve as the project grows. Documentation will be updated when architectural decisions change.

---

## 🧭 Knowledge Domains

### Geography

Structured information related to Nepal's geographical divisions and related information.

### History

Information covering historical periods, events, figures, and related historical structures.

### Culture

Information related to Nepal's cultural diversity, traditions, festivals, languages, art forms, and related subjects.

### Destinations

Information related to places and tourism destinations in Nepal, including destination-related data and supporting information.

### Wildlife

Information related to Nepal's wildlife, protected areas, species, flora, lakes, and related subjects.

### Education

Structured information related to educational institutions, programs, examinations, scholarships, rankings, and related educational information.

### Healthcare

Information related to healthcare facilities, hospitals, specialties, and related healthcare information.

> The presence of a domain in this list does not mean that every possible feature within that domain has been implemented.

---

## 📚 Documentation Structure

The documentation is organized around the areas that are useful to users, contributors, and developers.

```text
know-nepal-docs/
│
├── README.md
│
├── about/
├── architecture/
├── domains/
├── data/
├── api/
├── engineering/
├── deployment/
├── security/
├── decisions/
├── contributing/
└── ai/
```

Not every directory or document is necessarily implemented yet. The documentation repository will grow alongside the project.

---

## 🚦 Project Status

Know Nepal is an **actively developed project**.

The current codebase contains implemented backend and frontend components across the seven knowledge domains, along with database migrations, authentication, testing, caching, API documentation support, and deployment configuration.

However, some areas are still evolving.

Documentation therefore uses explicit status labels when appropriate:

| Status          | Meaning                                                   |
| --------------- | --------------------------------------------------------- |
| **Implemented** | Exists in the current implementation                      |
| **Partial**     | Some implementation exists, but the feature is incomplete |
| **Planned**     | Intended for future development                           |
| **Proposed**    | A recommendation that has not been adopted                |
| **Historical**  | Belongs to an earlier implementation or architecture      |
| **Deprecated**  | No longer used                                            |
| **Unknown**     | Cannot currently be verified                              |

---

## 🤝 Contributing

Know Nepal is being developed with the long-term goal of allowing broader community participation.

If you want to contribute, start by understanding:

1. What Know Nepal is trying to accomplish.
2. The current architecture.
3. The relevant knowledge domain.
4. The existing contribution guidelines.
5. The current implementation before proposing changes.

Contribution documentation will be expanded as the project establishes its community processes.

---

## 🧑‍💻 For Developers

Know Nepal currently consists of:

* **Backend:** Spring Boot modular monolith
* **Frontend:** Next.js / React
* **Database:** PostgreSQL
* **Database migrations:** Flyway
* **Authentication:** JWT-based authentication
* **Caching:** Caffeine
* **API documentation:** OpenAPI / Springdoc
* **Containerization:** Docker

For implementation-specific information, see the engineering and architecture documentation.

---

## 🤖 AI-Assisted Development

Know Nepal may be developed with AI-assisted development tools.

AI assistance is considered a development tool rather than an architectural characteristic of the project.

The important source of truth remains:

> **The actual Know Nepal source code and configuration.**

AI-generated suggestions should therefore be checked against the current implementation before being treated as project facts.

A concise AI/developer context will be maintained separately to help development agents understand the project without duplicating the entire documentation system.

---

## 🔐 Security

Security-sensitive information is intentionally **not documented here**.

This repository will never intentionally contain:

* Passwords
* API keys
* JWT secrets
* Database credentials
* Access tokens
* Private certificates
* Other sensitive credentials

Environment-specific secrets should be supplied through appropriate environment or secret-management mechanisms.

Security documentation will describe **how the system works**, without exposing sensitive values.

---

## 📌 Documentation Principles

The documentation follows a few simple principles:

### Accuracy over marketing

Know Nepal should be documented as it actually exists.

We avoid unsupported claims such as:

* "Enterprise-grade"
* "Revolutionary"
* "Highly scalable"
* "World-class"
* "Production-ready"

unless there is concrete evidence supporting such a statement.

### Current implementation over historical architecture

Older architectural experiments may be documented as historical context, but they should not be confused with the current architecture.

### Clear status

Implemented, partial, planned, proposed, historical, deprecated, and unknown functionality should remain clearly separated.

### Keep documentation maintainable

Documentation should explain important concepts without becoming a second copy of the entire source code.

### Keep sensitive information private

Public documentation should help people understand and contribute to Know Nepal without exposing credentials, secrets, or unnecessary internal security information.

---

## 🗺️ Documentation Roadmap

The documentation will be developed gradually.

Planned areas include:

* [ ] Project overview
* [ ] Architecture overview
* [ ] Modular monolith architecture
* [ ] Domain documentation
* [ ] Database overview
* [ ] API documentation
* [ ] Local development guide
* [ ] Testing guide
* [ ] Deployment guide
* [ ] Security overview
* [ ] Contribution guide
* [ ] Architecture Decision Records
* [ ] AI/developer project context

---

## 🌱 Why Know Nepal?

Nepal contains a large amount of knowledge across geography, history, culture, destinations, wildlife, education, healthcare, and many other areas.

Know Nepal aims to organize useful information into a structured platform so that it can become easier to:

**Discover → Understand → Maintain → Contribute**

The project is being built incrementally, with the current implementation taking priority over future plans.

---

## 📄 Documentation Status

This documentation repository is itself a work in progress.

If something is not documented yet, that does not necessarily mean the corresponding feature does not exist. The source code remains the authoritative source for implementation details.

---

**Know Nepal**
*Building a structured digital knowledge platform for Nepal.*
