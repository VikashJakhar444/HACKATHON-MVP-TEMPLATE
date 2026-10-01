# Database & Data Persistence Standards

## Purpose
This document establishes data modeling, storage engine selection, and data integrity standards for hackathon MVPs. It ensures data is stored reliably, queried efficiently, and protected against corruption without introducing heavy database infrastructure.

---

## 1. Storage Selection Hierarchy (Simplest Viable Tool)

Choose the simplest persistence mechanism that reliably satisfies the data model and concurrency requirements:

1. **Tier 1: In-Memory / Structured File Storage (`JSON` / `CSV` / `LocalStorage`)**
   - *Best For*: Single-user desktop tools, read-mostly lookup tables, lightweight state persistence.
   - *Advantage*: Zero external dependencies, human-readable, instant setup.
2. **Tier 2: Embedded Relational Database (`SQLite`) — Primary Default**
   - *Best For*: Relational data, indexed queries, structured entity relationships, ACID safety.
   - *Advantage*: Zero server setup, stored as a single file, supported natively across Python/Node/Go.
3. **Tier 3: Client-Side Embedded Storage (`IndexedDB` / `DuckDB-WASM`)**
   - *Best For*: Heavy client-side analytical queries or offline web applications.
4. **Tier 4: Remote Relational / Document Server (`PostgreSQL` / `MongoDB`)**
   - *Best For*: Multi-user concurrent writes, complex geospatial querying, or cloud deployments.
   - *Constraint*: Must be explicitly justified by problem requirements. **Do NOT choose PostgreSQL automatically.**

---

## 2. Minimalist Data Modeling

- **Entity Justification**: Every table or JSON entity must map directly to a verified requirement in `docs/04-product/PRD_TEMPLATE.md`.
- **Avoid Over-Normalization**: 2–4 cohesive entities are typical for a 24-hour MVP. Do not create 15 micro-tables with extensive junction tables unless required.
- **Explicit Schemas**: Document all entity schemas in `docs/06-architecture/DATA_MODEL_TEMPLATE.md` with:
  - Explicit column types
  - Primary keys and foreign key constraints
  - Mandatory (`NOT NULL`) vs. Optional fields
  - Default values and timestamps (`created_at`, `updated_at`)

---

## 3. Data Integrity & Safety

- **Parameterized Queries**: Always use parameterized queries (e.g., `cursor.execute("SELECT * FROM users WHERE id = ?", (user_id,))`) to prevent SQL Injection. Never concatenate strings into SQL statements.
- **Transaction Safety**: Wrap multi-table mutation operations in atomic transactions (`BEGIN` ... `COMMIT` / `ROLLBACK`).
- **Validation Before Persistence**: Validate data types, lengths, and business constraints in application memory *before* issuing database writes.

---

## 4. Demo Data & Fixture Governance

Strictly distinguish between three distinct categories of data:

| Data Category | Definition & Scope | Integrity Rule |
| :--- | :--- | :--- |
| **`REAL DATA`** | Live inputs submitted during active application execution. | Must be processed by genuine computation. |
| **`DEMO FIXTURES`** | Verified sample datasets pre-loaded for consistent live demonstration. | Must be labeled as `DEMO FIXTURE` in the UI and docs. |
| **`TEST DATA`** | Unit/integration test cases used to verify edge cases and failure modes. | Stored strictly in `tests/` or fixture directories. |

> **CRITICAL ETHICAL RULE**: Never fabricate demo data and represent it to judges as real-world production evidence or empirical benchmark output.

---

## 5. Migration Discipline for 24-Hour MVPs

- **No Heavy Migration Frameworks**: Avoid setting up Alembic, Prisma migrations, or Flyway for simple MVP prototypes unless complex evolving schemas require it.
- **Simple Schema Initialization**: Use an idempotent initialization script (e.g., `CREATE TABLE IF NOT EXISTS ...`) executed automatically on application startup.
