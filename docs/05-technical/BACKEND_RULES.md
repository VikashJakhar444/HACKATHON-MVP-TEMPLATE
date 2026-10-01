# Backend Engineering Standards

## Purpose
This document establishes framework-agnostic backend engineering standards for hackathon MVP development. It ensures server-side and business-logic code is robust, deterministic, secure, and easily testable without imposing specific backend runtimes or distributed complexity.

---

## 1. Backend Architecture & Modularity

- **Default Preference: Modular Monolith**: Build a single, cohesive, self-contained backend process.
  - Keep separation of concerns clean via modular directories/modules (e.g., `routes/`, `services/`, `models/`, `utils/`).
  - Strictly avoid microservices, multi-process RPC meshes, or distributed queues unless the problem domain explicitly mandates physical process separation.
- **Single Responsibility**: Each module, class, or function must have one clear, well-defined operational responsibility.

---

## 2. Core Backend Responsibilities

The backend/core logic layer is the authoritative source of truth for:
1. **Core Business Logic**: Executing primary algorithms, heuristic transformations, and differentiators.
2. **Authoritative Input Validation**: Validating types, bounds, and structures independent of client-side checks.
3. **Data Integrity & Persistence**: Managing local storage transactions, schemas, and file I/O safely.
4. **External Service Integrations**: Communicating with third-party APIs, enforcing rate limits, and implementing fallbacks.
5. **Security & Cryptographic Operations**: Protecting credentials, hashing data, and managing sessions where required.

> **Rule**: Never duplicate business logic across client and server. Keep computation centralized on the backend or in dedicated business logic modules.

---

## 3. Strict Input Handling & Sanitization

The backend must adopt a **Zero-Trust Input Policy**:
- **Never Trust Input**: Treat all user inputs, HTTP payloads, query strings, headers, uploaded files, and even third-party API responses as untrusted.
- **Strict Schema Validation**: Parse and validate all incoming data payloads against defined schemas before processing.
- **Boundary & Type Constraints**: Enforce maximum string lengths, numerical ranges, allowed enum values, and non-empty rules.
- **Fail Fast & Safely**: Reject invalid payloads immediately with clear validation error codes.

---

## 4. Predictable Error Handling & Resilience

- **Deterministic Failure States**: Every operation that performs I/O, file access, mathematical division, or network calls must be wrapped in structured exception handling.
- **Non-Destructive Failures**: Errors must never leave data storage in a corrupted, half-written, or locked state.
- **No Stack Traces in Responses**: Never expose raw stack traces, database schemas, or internal file paths to client responses. Return clean, human-readable error envelopes.

---

## 5. Configuration & Secret Management

- **Environment-Driven Configuration**: Use environment variables (`.env`) for runtime settings (port, debug mode, external API keys).
- **Zero Hardcoded Secrets**: Strictly forbid embedding API keys, database passwords, private tokens, or authentication secrets in code.
- **Safe Defaults**: The application should provide sane default configurations for local development without requiring manual secret setup for basic offline features.

---

## 6. Deterministic Reliability & Testability

- **Pure Functions Where Possible**: Design business logic transformations as pure or nearly pure functions to maximize unit testability.
- **Inspectable State**: Make application state easily queryable for automated verification scripts.
- **Graceful Shutdown**: Handle termination signals (`SIGINT`, `SIGTERM`) cleanly, flushing buffers and closing database connections.

---

## 7. Operational Logging Discipline

- **Purposeful Logs**: Log informative operational events (startup, core action triggers, third-party API latency, recoverable warnings, unhandled errors).
- **Sanitized Log Streams**: Never log sensitive user inputs, passwords, API tokens, or personal identifiable information (PII) to console or disk log files.
