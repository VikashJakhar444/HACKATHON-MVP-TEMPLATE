# API Engineering & Boundary Standards

## Purpose
This document defines the engineering standards, protocol requirements, and boundary conditions for APIs in hackathon projects. It explicitly establishes that APIs are conditional tools, not mandatory architectural dogma.

---

## 1. "API-First" is NOT a Universal Rule

> **CORE PRINCIPLE**: Do NOT create a network API layer merely because modern web applications commonly have one.

### Use Direct Function / Module Calls When:
- The frontend and backend reside in the same runtime (e.g., Python GUI, server-rendered templates, or unified desktop application).
- Network serialization adds latency, boilerplate, and failure modes without architectural benefit.

### Create an API Layer ONLY When:
1. **Physical Client/Server Separation**: A decoupled browser single-page app (SPA) communicates with an independent backend server.
2. **External Integration**: Third-party services or sponsor platforms need programmatic access.
3. **Multi-Client Support**: The same backend services both a web dashboard and a mobile/CLI client.
4. **Isolated Service Boundary**: A specific computationally heavy service runs on a dedicated host or container.

---

## 2. API Contract & Specification Standards

If an API layer is justified, every endpoint must be documented in `docs/06-architecture/API_SPEC_TEMPLATE.md` with:
- **HTTP Method & Path**: RESTful conventions (e.g., `POST /api/v1/analyze`).
- **Functional Purpose**: Exact capability executed.
- **Input Payload Schema**: Accepted JSON types, mandatory fields, and bounds.
- **Validation Rules**: Specific constraints triggering `400 Bad Request`.
- **Output Schema**: Deterministic JSON response payload.
- **Error States & Status Codes**: Explicit error codes for invalid inputs, missing resources, and server errors.
- **Authentication**: Explicitly stated as `None`, `Session-based`, or `Token-based`.

---

## 3. Standardized Response Envelopes

All JSON responses must conform to a predictable structure:

### Standard Success Envelope (`200 OK` / `201 Created`):
```json
{
  "success": true,
  "data": {
    "result_id": "res-9876",
    "status": "COMPLETED",
    "payload": {}
  },
  "metadata": {
    "timestamp": "2026-10-01T10:18:00+05:30",
    "execution_time_ms": 38
  }
}
```

### Standard Error Envelope (`400` / `404` / `500`):
```json
{
  "success": false,
  "error": {
    "code": "INVALID_INPUT_LENGTH",
    "message": "The input text exceeds the allowed limit of 5000 characters.",
    "details": []
  }
}
```

> **Security Rule**: Never return raw server exception stack traces or database schema fragments in error payloads.

---

## 4. API Security & Request Hygiene

- **Content-Type Enforcement**: Validate `Content-Type: application/json` on incoming mutation requests.
- **Payload Size Limits**: Enforce maximum body size limits (e.g., max 2MB for JSON payloads; max 10MB for file uploads) to prevent Denial of Service.
- **CORS Restraints**: In local development, restrict Cross-Origin Resource Sharing (CORS) to the explicit local client origin (`http://localhost:*`).

---

## 5. The API Anti-Complexity Rule

Do **NOT** introduce the following heavy API abstractions during a 24-hour hackathon unless explicitly required:
- ❌ GraphQL schemas and resolvers (use simple REST/JSON endpoints).
- ❌ gRPC / Protocol Buffers (use standard JSON over HTTP).
- ❌ WebSocket servers for basic synchronous operations (use simple HTTP POST/GET).
- ❌ Distributed API Gateways, Service Meshes (Istio), or Reverse Proxy meshes.
- ❌ Asynchronous message brokers (Kafka, RabbitMQ, Celery) when in-process background threads or synchronous execution suffice.
