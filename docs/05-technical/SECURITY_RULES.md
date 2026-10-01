# Security & Data Protection Standards

## Purpose
This document establishes practical, high-impact security standards for hackathon MVPs. It ensures the application is built safely without introducing enterprise security overhead or blocking rapid 24-hour development.

---

## 1. The Proportional Threat Model Rule

> **CORE PRINCIPLE**: Security must be proportional to the actual operational context of the MVP.

- **For Local Prototypes / Single-User MVPs**: Focus on input sanitization, safe I/O, secret protection, and preventing local injection. Do not spend time configuring OAuth2 servers, SSO, or multi-factor authentication.
- **For Web-Hosted Deployments**: Implement baseline web hygiene (CORS, input bounds, rate limits, HTTPS).
- **Non-Negotiable Baseline**: **Never knowingly introduce obvious, severe vulnerabilities (e.g., raw SQL injection, plain-text credential leaks, or arbitrary code execution).**

---

## 2. Secrets & Credential Management

- **Zero Hardcoded Secrets**: Strictly forbid storing API keys, private tokens, passwords, or encryption keys in source code or git commits.
- **Environment Variables**: Load all external credentials from local environment variables via `.env` (with `.env.example` committed to define expected keys).
- **Git Ignore**: Ensure `.env`, `*.pem`, `*.key`, and credential files are included in `.gitignore`.

---

## 3. Input Validation & Injection Prevention

- **SQL / Query Injection**: Always use parameterized queries or safe ORM access. Never interpolate unescaped strings directly into database commands.
- **Cross-Site Scripting (XSS)**: Never render unescaped user-generated text via `innerHTML` or `dangerouslySetInnerHTML`. Use `textContent`, standard DOM properties, or safe templating engines.
- **Command Injection**: Never pass unsanitized user inputs into system shell execution commands (`os.system()`, `exec()`, `eval()`). Use parameterized subprocess execution with explicit argument lists.
- **Path Traversal**: Validate and sanitize all file paths requested by users. Reject paths containing `../` or absolute system roots to prevent arbitrary file access.

---

## 4. Conditional Authentication & Authorization

- **Authentication is CONDITIONAL**: Do NOT build login/registration systems unless:
  1. The core problem statement explicitly requires user identity and distinct accounts.
  2. User-specific data isolation is a critical functional requirement.
- **Server-Side Authorization**: If multiple roles exist, enforce permissions **strictly on the backend/server-side**. Never rely on hiding frontend buttons as the sole security control.

---

## 5. File Upload Safety

If the application accepts file uploads:
1. **Type Whitelisting**: Validate file extensions and MIME types against an explicit whitelist (e.g., only `.json`, `.csv`, `.png`).
2. **Size Enforcement**: Enforce strict upload size limits (e.g., max 5MB–10MB) to prevent buffer overflows and disk exhaustion.
3. **Safe Storage**: Store uploaded files in an isolated temporary directory; never upload directly into executable script paths.
4. **Error Handling**: Gracefully reject malformed, corrupted, or zero-byte files without crashing.

---

## 6. Information Leakage & Error Security

- **Sanitized Client Responses**: Never send raw Python tracebacks, Java stack traces, database schema errors, or internal file paths to client browsers.
- **Sanitized Terminal & Disk Logs**: Never print raw authentication tokens or user passwords into console output or persistent log files.

---

## 7. Dependency Security & Minimal Attack Surface

- **Minimize Third-Party Packages**: Every external library increases the security attack surface and introduces supply-chain risks.
- **Built-in Tools First**: Prefer standard language libraries (e.g., Python standard library, standard browser APIs) over obscure single-utility npm/pip packages.
