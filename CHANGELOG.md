# Changelog

All notable changes to AES are documented in this file.

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
