# Security Policy

## Supported Versions

| Repository | Supported |
|------------|-----------|
| mechanicsdsl (core) | ✅ Latest stable |
| mechanicsdsl-embedded | ✅ Latest |
| mechanicsdsl-ros2 | ✅ Latest |
| mechanicsdsl-unity | ✅ Latest |
| mechanicsdsl-notebooks | ✅ Latest |
| mechanicsdsl-datasets | ✅ Latest |

## Reporting a Vulnerability

Please **do not** open a public GitHub issue for security vulnerabilities.

Report vulnerabilities privately by emailing: **nomapa223@gmail.com**

Include:
- A description of the vulnerability
- Steps to reproduce
- Potential impact
- Any suggested mitigations

You can expect an acknowledgment within 48 hours and a resolution timeline within 7 days for critical issues.

## Scope

Security issues in MechanicsDSL are most likely to arise in:
- The FastAPI WebSocket server (`mechanicsdsl-core[server]`)
- DSL input parsing (potential for malformed input to cause unexpected behaviour)
- Docker container configurations
- Dependency vulnerabilities (reported via Dependabot)

Numerical correctness issues (wrong physics) are not security vulnerabilities but are equally important — please report them as bugs.
