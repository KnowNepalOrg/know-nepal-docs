# Education

## Overview

The **Education** domain provides structured information about
education and academic opportunities across Nepal.

It allows users to explore educational institutions, programs, and
academic resources.

---

## Domain Scope

The Education domain covers:

- Schools
- Colleges
- Universities
- Programs
- Scholarships
- Entrance exams

---

## Data

Education data is stored within the Education domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Education domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the Education domain
while sharing common backend infrastructure with the other domains.

---

## API

The Education domain exposes its functionality through the Know Nepal
REST API.

The frontend accesses education information through the backend API
rather than directly accessing the database.

---

## Domain Boundary

The Education domain owns education-related information and data.

Other domains should interact with Education through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
