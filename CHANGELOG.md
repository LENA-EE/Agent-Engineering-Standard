# Changelog

All notable changes to AES are documented in this file.

---

## v1.3 (2026-05-28)

### Added
- **§3.2 Acceptance Floor (invariant)** — named, callable invariant: the REVIEW → DEPLOYMENT transition is gated by an explicit act of human acceptance. No project setting, complexity classification, simplicity allowance, or successful verification result removes this gate. The subject of acceptance is always a Human.
- **Verification-first triple** — PLANNING now requires the Agent to declare the verification approach. Where acceptance criteria exist (in `spec.md` or the constitution), the verification approach **MUST** cover them; the Agent **MUST NOT** narrow the bar. The verification declaration is **NOT** subject to simplification.
- **REVIEW state composed of three distinct ordered activities**: (1) self-review, (2) verification execution, (3) acceptance by the Human. The Agent **MUST NOT** self-issue acceptance.
- **REVIEW → EXECUTION** is now reachable from three sources: self-review findings, verification execution findings, or rejection raised at acceptance (e.g., insufficient verification approach).
- **Operational-mechanisms anchor** in §3.2 — branching policy, merge workflow, and release gating *express* acceptance but do not substitute for the invariant (placeholder for forthcoming Branching & Review Policy).

### Changed
- **§3 State Model** restructured: state definitions promoted to §3.1; new §3.2 Acceptance Floor.
- **§4 EXECUTION → REVIEW gate** is now stack-agnostic: "the project's defined integrity check passes (compilation, build, lint, smoke test, syntax + import resolution — whichever the stack defines)" instead of "no compilation/build errors". Same logic, written into the norm instead of guessed from the stack.
- **§4 PLANNING → EXECUTION gate**: plan/spec formality is partially compressible per the simplicity rule; verification declaration is NOT compressible; `plan.md` approval is required only for non-trivial changes.
- **§4 REVIEW → DEPLOYMENT gate** explicitly references §3.2 Acceptance Floor; verification results, however strong, do not constitute acceptance — they are evidence on which the Human's acceptance decision is made.
- **Compressibility framing** made explicit across §4: which transitions are partially compressible (PLANNING), which are non-compressible (REVIEW → DEPLOYMENT under the Acceptance Floor).

---

## v1.2 (2026-05)

### Added
- **Protected Resources** section (§10) — hard boundaries around system config, database, git identity, credentials. Agent must stop and ask before modifying any protected resource.
- **Secrets prohibition** — `❌ Secrets in source code` added to Forbidden Practices.
- **Agent Boundaries** section (§9) — explicit list of what agent must not do without permission / ever.
- **Security section** in PROJECT_CONSTITUTION template — PII, secrets, agent boundaries, MCP server rules.
- `/spec` command — create feature specification.
- `/constitution --quick` mode — 3 questions instead of 7 for fast setup.
- LICENSE (MIT).
- .gitignore.
- CHANGELOG.md (this file).

### Changed
- **Language-agnostic** — removed TypeScript-specific rules (`strict mode`, `no any`). Now works with any stack. Replaced with universal "use typing available in the project's stack".
- **Removed 150 LOC file limit** — replaced with "compact and focused" principle.
- **State transitions** now require verifiable artifacts (spec.md, plan.md) instead of subjective "context understood".
- **Compliance levels** (L1–L4) tied to verifiable artifacts, not declarations.
- **UX states** upgraded from SHOULD to MUST (loading, empty, error).

### Removed
- Communication Semantics section — self-evident for any LLM agent.
- Project Context section in CLAUDE.md — duplicated constitution.
- Redundant yes.png.

---

## v1.1 (2026-02)

### Added
- RFC-grade specification format.
- State machine model for agent execution.
- Forbidden Practices list.
- Compliance Levels L1–L4.
- Command interface (/constitution, /explore, /plan, /status, /fix, /review, /deploy).

---

## v1.0 (2026-02)

### Added
- Initial release.
- PROJECT_CONSTITUTION.md template.
- CLAUDE.md execution contract.
