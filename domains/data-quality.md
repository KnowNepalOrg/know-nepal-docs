# Data Quality

## Purpose

This document defines guidelines for maintaining accurate, consistent, and useful data across Know Nepal's domain modules.

These guidelines help contributors review existing records and maintain data quality as the platform grows.

## Core Principles

### Accuracy

- Verify factual information using reliable sources.
- Avoid adding unverified claims as established facts.
- Recheck information when conflicting sources are found.

### Source Reliability

- Prefer official government sources, recognized institutions, and authoritative publications where appropriate.
- Use reputable secondary sources when primary sources are unavailable.
- Record source information when supported by the data model or contribution workflow.

### Consistency

- Follow existing naming and formatting conventions.
- Use consistent date formats, units, terminology, and categories.
- Keep related records and geographic relationships consistent.

### Completeness

- Include the information required for each record type.
- Avoid inventing values to fill missing information.
- Represent unknown or unavailable information appropriately.

### Uniqueness

- Check for existing records before adding new ones.
- Avoid duplicate places, organizations, events, and other entities.
- Review potential duplicates before merging or removing records.

### Timeliness

- Identify information that may change over time, such as public services, educational programs, and travel information.
- Recheck time-sensitive information when updates are needed.
- Avoid presenting potentially outdated information as recently verified.

## Data Verification Workflow

Before adding or updating a record:

1. Identify the information that needs to be added or corrected.
2. Check whether a relevant record already exists.
3. Verify important facts against reliable sources.
4. Check names, dates, relationships, and required fields.
5. Review the change for consistency with existing records.
6. Test relevant validation rules or checks when available.
7. Document the source or reason for the change where appropriate.

## Handling Uncertain Information

- Do not present uncertain information as confirmed fact.
- Seek additional sources when reliable references conflict.
- Leave unsupported details out rather than inventing them.
- Escalate significant unresolved discrepancies for review.

## Validation and Maintenance

Data validation should be applied at the appropriate level, including:

- Required-field checks
- Format and value validation
- Duplicate detection
- Relationship and reference integrity
- Domain-specific business rules

The checks available depend on the current application, database schema, and validation tooling.

## Scope

These guidelines apply to data maintained across Know Nepal's domain areas, including Geography, History, Culture, Wildlife, Education, Healthcare, and Destinations.

Domain-specific requirements should be documented alongside the relevant domain documentation when necessary.

## Related Documentation

- [Data Architecture](../architecture/data.md)
- [Current Project State](../status/current-state.md)
- [Contributing Guidelines](../contributing/workflow.md)
