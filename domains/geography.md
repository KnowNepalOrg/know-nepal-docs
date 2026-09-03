# Geography

## Overview

The **Geography** domain manages structured geographic and
administrative information about Nepal.

It provides the data and functionality required to represent Nepal's
administrative divisions and related geographic information.

---

## Domain Scope

The Geography domain covers:

- Provinces
- Districts
- Municipalities
- Wards
- Geographic relationships between administrative levels

The domain is responsible for maintaining the relationships between
these administrative entities.

---

## Data

Geographic data is stored in the Geography domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Geography domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the Geography domain
while sharing common backend infrastructure with the other domains.

---

## API

The Geography domain exposes its functionality through the Know Nepal
REST API.

Frontend applications access geographic data through the backend API
rather than accessing the database directly.

---

## Domain Boundary

The Geography domain owns geographic and administrative data.

Other domains should interact with Geography through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
