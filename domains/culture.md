# Culture

## Overview

The **Culture** domain provides structured information about the
cultural diversity and traditions of Nepal.

It allows users to explore festivals, ethnic groups, languages, art
forms, and traditional attire.

---

## Domain Scope

The Culture domain covers:

- Festivals
- Ethnic groups
- Languages
- Art forms
- Traditional attire

---

## Data

Cultural data is stored within the Culture domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Culture domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the Culture domain while
sharing common backend infrastructure with the other domains.

---

## API

The Culture domain exposes its functionality through the Know Nepal
REST API.

The frontend accesses cultural information through the backend API
rather than directly accessing the database.

---

## Domain Boundary

The Culture domain owns cultural information and related data.

Other domains should interact with Culture through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
