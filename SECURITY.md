# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in Aether, please report it responsibly.

**Do NOT open a public GitHub issue for security vulnerabilities.**

Instead, please email: **security@aether.dev** (or the maintainer's private email)

Include:

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

## Response Timeline

| Stage              | Timeframe                                         |
| ------------------ | ------------------------------------------------- |
| Acknowledgment     | Within 48 hours                                   |
| Initial assessment | Within 1 week                                     |
| Fix or mitigation  | Within 2 weeks (critical), 1 month (non-critical) |

## Scope

The following are in scope:

- Backend API (`apps/api`)
- Frontend web app (`apps/web`)
- Chrome Extension (`apps/extension`)
- Authentication and authorization bypass
- Injection vulnerabilities (SQL, prompt injection, XSS)
- Insecure direct object references
- Server-side request forgery

## Out of Scope

- Denial of service attacks
- Social engineering
- Issues in third-party dependencies (report upstream)

## Supported Versions

| Version           | Supported   |
| ----------------- | ----------- |
| Latest main       | Yes         |
| Previous releases | Best-effort |

## Security Measures

Aether implements the following security practices:

- Clerk JWT verification on all API requests
- AES-256-GCM encryption for stored OAuth tokens
- Row-level security on PostgreSQL tables
- Prompt injection defense (email content treated as data, never instructions)
- Approval gate enforced at API layer (not just UI)
- Webhook signature verification (Clerk, Gmail)
- CORS locked to known origins in production
- Per-user, per-integration rate limiting

## Disclosure Policy

We follow coordinated disclosure. Once a fix is available, we will:

1. Credit the reporter (unless anonymity is requested)
2. Publish a security advisory
3. Tag a patched release
