# 📜 PROJECT CONSTITUTION

## Canonical Project Constitution (AI Engineering Standard — AES)

AES Constitution Version: 1.2
Status: Active
Authority Level: Required

---

## ⚖️ CONSTITUTION AUTHORITY

This document defines the **architectural and product authority** of the project.

All AI agents and contributors operating in this repository MUST:

- follow decisions defined in this constitution
- avoid architectural deviation
- request clarification when conflicts appear
- prioritize this document over assumptions

If implementation contradicts this constitution —
**the constitution prevails.**

This file acts as the **single source of truth** for the system.

---

## 🤖 AI EXECUTION CONTEXT

AI agents MUST:

1. Read this constitution before generating code
2. Produce a specification and implementation plan
3. Execute work incrementally
4. Validate changes against defined constraints

🚫 Implementation MUST NOT begin without alignment.

---

# 1. 🎯 PRODUCT SCOPE

## Project Description

Name:
One-sentence description:
Target user:

---

## MVP Scope (≤5 items)

1.
2.
3.

---

## Non-Goals

❌
❌
❌

---

## Success Metrics

| Metric | Target | Measurement |
| --- | --- | --- |
| Core feature works | Yes | Smoke test |
| Response time | < ___ sec | P95 latency |
| Test coverage | > ___% | CI |

---

# 2. 🛠️ TECHNOLOGY STACK

> Adapt sections to your project type. Add components you have, remove what doesn't apply.
> Examples: web frontend · backend API · mobile app · CLI tool · library / SDK · ML pipeline · desktop app · embedded firmware · DevOps service.

## Components

For each runtime component of your project:

### {Component name}

- Type:
- Language:
- Framework:
- Key dependencies:
- Storage / persistence (if applicable):

### {Add more components as needed}

---

## Shared / Infrastructure

- Package manager:
- Runtime / build target:
- Deployment:
- Hosting / distribution:

---

# 3. 📐 ARCHITECTURE

## Architectural Approach

- Pattern:
- Layer separation:
- API isolation:
- Error handling:

---

## Project Structure

> Describe the actual structure of your project. Example below — adapt to your stack's conventions.

```
src/
├── api/
├── components/
├── pages/
├── hooks/
├── utils/
└── types/
```

---

# 4. 👤 USER FLOWS

FLOW 1:
User → Action → Result

FLOW 2:
User → Action → Result

---

# 5. 📋 FUNCTIONAL REQUIREMENTS

## User Stories

P0 — Must Have:

As a user I want ___

P1 — Should Have:

P2 — Nice to Have:

---

# 6. ⚡ NON-FUNCTIONAL REQUIREMENTS

> Pick metrics that fit your project type.

## Performance

- Primary response / latency target:
- Secondary metric (size / memory / startup / inference time):
- Throughput target (if applicable):

## Reliability

- Availability / uptime target:
- Health / readiness signal: (e.g., HTTP `/health` → 200, systemd ready, process exit code 0, smoke test passes)
- Failure recovery strategy:

---

# 7. 🔒 SECURITY

## Forbidden in source code

- Secrets, tokens, API keys, passwords
- Personally identifiable information (PII)
- Internal IPs, hostnames, environment URLs
- Direct requests to production API from dev code

## Agent boundaries

- Push to main/master/release branches: FORBIDDEN
- Modify CI/CD pipelines: FORBIDDEN
- Access production data: FORBIDDEN
- Create/delete infrastructure: FORBIDDEN

## MCP Servers (if applicable)

- Default mode: read-only
- API keys: via vault / environment variables
- Registration: every server in team registry

---

# 8. 🗄️ DOMAIN MODEL

Entity1 1:M Entity2

---

# 9. 🚀 DEPLOYMENT

- Platform:
- Environment variables:
- CI/CD:
- Rollback strategy:

---

# 10. ✅ ACCEPTANCE CRITERIA

A feature is complete when:

- [ ] Happy path works
- [ ] Errors handled
- [ ] Zero type errors
- [ ] Loading / Empty / Error states implemented
- [ ] Destructive actions require confirmation
- [ ] No AES violations (hardcoded config, suppressed errors, empty catch, secrets)
- [ ] Code reviewed

---

# 🔁 CONSTITUTION EVOLUTION

Changes require:

- explicit human approval
- architectural review
- version update

---

*AI Engineering Standard (AES) v1.3*
