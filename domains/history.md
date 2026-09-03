# History

## Overview

The **History** domain provides structured information about the
history of Nepal.

It allows users to explore major historical periods, dynasties,
events, and notable historical figures.

---

## Domain Scope

The History domain covers:

- Historical eras
- Dynasties
- Historical events
- Notable figures

---

## Data

Historical data is stored within the History domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The History domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the History domain while
sharing common backend infrastructure with the other domains.

---

## API

The History domain exposes its functionality through the Know Nepal
REST API.

The frontend accesses historical information through the backend API
rather than directly accessing the database.

---

## Domain Boundary

The History domain owns historical information and related data.

Other domains should interact with History through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
