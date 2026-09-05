# Contribution Workflow

## Overview

Contributions to Know Nepal should follow a consistent workflow to keep
changes understandable, reviewable, and aligned with the project's
architecture.

The workflow applies to application code, documentation,
infrastructure, and other project changes.

---

## 1. Understand the Change

Before making a change:

- Understand the problem being solved.
- Identify the repository responsible for the change.
- Review the existing implementation and related documentation.
- Check whether an existing component or pattern can be reused.

For architectural or cross-cutting changes, review the relevant
architecture documentation and Architecture Decision Records.

---

## 2. Create a Branch

Changes should be developed on a dedicated branch rather than directly
on the main development branch.

Use a descriptive branch name that communicates the purpose of the
change.

Examples:

```text
feature/destination-filtering
fix/trip-planner-auth
docs/update-security
