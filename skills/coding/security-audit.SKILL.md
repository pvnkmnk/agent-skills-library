---
name: security-audit
description: Audits code for OWASP Top 10 vulnerabilities, injection flaws, authentication weaknesses, secrets in source, and insecure dependencies.
category: coding
tags: [coding, security, owasp, audit, vulnerabilities, auth]
agents: [opencode, freebuff, antigravity, codex]
---

# security-audit

## Purpose

Systematic code security review targeting OWASP Top 10 and common implementation flaws. Produces an actionable remediation list ranked by severity.

## Invocation

**OpenCode / Codex:** `Invoke security-audit`
**Freebuff:** `/skill security-audit`

## Audit Checklist

### Injection
- SQL injection via unsanitised user input
- Command injection in subprocess calls
- LDAP / XPath / NoSQL injection

### Broken Authentication
- Hardcoded credentials
- Weak session token generation
- Missing token expiry or rotation

### Sensitive Data Exposure
- Secrets in source code or env vars committed to git
- PII in logs
- Unencrypted storage of sensitive data

### Security Misconfiguration
- Debug mode enabled in production
- Open ports or services without auth
- Default credentials not changed

### Vulnerable Dependencies
- Known CVEs in pinned package versions
- Unpinned dependencies

### Access Control
- Missing authorisation checks
- Privilege escalation paths
- IDOR vulnerabilities

## Inputs

- Code file, module, or diff to audit
- Language and framework
- Deployment context (public-facing, internal, local)

## Outputs

- Finding list: severity (Critical/High/Medium/Low), location (file:line), description, remediation
- Summary counts by severity
- Quick-win remediations vs. architectural fixes

## Failure Modes

- **Code is minified or obfuscated** — surface limitation; audit what is readable.
- **Dependencies list is unavailable** — note the gap; cannot audit transitive dependencies.

## Companion Skills

- `authz-and-audit-log` — implement missing auth controls found in audit
- `tdd-loop` — write regression tests for fixed vulnerabilities
- `git-safe-ops` — ensure fixes are committed safely
