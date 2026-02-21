# Generic Security Rules

Use these as universal security guardrails for any project, regardless of language, framework, or platform.

## Rule 1
- Rule ID: `GEN-A01`
- Category: `Broken Access Control`
- Priority: `critical`
- Rule: Enforce authorization on every protected action and resource.
- Checks:
  - Access is denied by default.
  - Users cannot access other users' data without explicit permission.
  - Privileged actions require privileged roles.

## Rule 2
- Rule ID: `GEN-A02`
- Category: `Cryptographic Failures`
- Priority: `critical`
- Rule: Protect sensitive data in transit and at rest with strong cryptography.
- Checks:
  - Sensitive data is identified and minimized.
  - Strong, modern crypto is used.
  - Plaintext secrets/passwords are never stored.

## Rule 3
- Rule ID: `GEN-A03`
- Category: `Injection`
- Priority: `critical`
- Rule: Treat all external input as untrusted and prevent interpreter injection.
- Checks:
  - Safe parameterized APIs are used for data/command operations.
  - Input is validated and constrained.
  - Dangerous dynamic execution paths are avoided.

## Rule 4
- Rule ID: `GEN-A04`
- Category: `Insecure Design`
- Priority: `high`
- Rule: Build security into architecture and requirements from the start.
- Checks:
  - Threats and abuse cases are documented for key flows.
  - Secure defaults and fail-safe behavior are defined.
  - Security acceptance criteria exist for new features.

## Rule 5
- Rule ID: `GEN-A05`
- Category: `Security Misconfiguration`
- Priority: `high`
- Rule: Use hardened, minimal, and environment-specific secure configuration.
- Checks:
  - Insecure defaults are removed.
  - Debug/excessive error detail is disabled in production.
  - Configuration is reviewed and validated regularly.

## Rule 6
- Rule ID: `GEN-A06`
- Category: `Vulnerable and Outdated Components`
- Priority: `high`
- Rule: Continuously track and patch dependency risk.
- Checks:
  - Dependency inventory is maintained.
  - Versions are pinned and updated.
  - Releases are blocked for unresolved critical vulnerabilities.

## Rule 7
- Rule ID: `GEN-A07`
- Category: `Identification and Authentication Failures`
- Priority: `critical`
- Rule: Implement strong authentication and secure session management.
- Checks:
  - Authentication controls resist brute-force abuse.
  - Sessions are rotated/invalidated on auth state changes.
  - High-risk operations have stronger authentication assurance.

## Rule 8
- Rule ID: `GEN-A08`
- Category: `Software and Data Integrity Failures`
- Priority: `high`
- Rule: Protect software supply chain and data integrity end to end.
- Checks:
  - Build/deploy artifacts come from trusted sources.
  - Integrity verification is used for critical artifacts.
  - CI/CD changes are controlled and auditable.

## Rule 9
- Rule ID: `GEN-A09`
- Category: `Security Logging and Monitoring Failures`
- Priority: `high`
- Rule: Log and monitor security-relevant events for timely detection and response.
- Checks:
  - Security events are logged with enough context.
  - Logs are protected from tampering and unauthorized access.
  - Alerts and response ownership are defined.

## Rule 10
- Rule ID: `GEN-A10`
- Category: `Server-Side Request Forgery (SSRF)`
- Priority: `high`
- Rule: Restrict and validate server-initiated outbound requests.
- Checks:
  - Outbound targets are restricted.
  - User-supplied URLs/endpoints are validated.
  - Internal/private destinations are blocked.
