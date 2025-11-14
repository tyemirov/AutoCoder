# AGENTS.md

## <Repo/App name>

<App purpose description. What does it do>. See README.md for details

## Document Roles

- NOTES.md: Read-only process playbook maintained by leads. Agents never edit it during implementation cycles.
- ISSUES.md: Append-only log of newly discovered requests and changes. No instructive sections live here; each entry records what changed or what was discovered.
- PLAN.md: Working plan for one concrete change/issue; ephemeral and replaced per change.

### Issue Status Terms

- Resolved: Completed and verified; no further action.
- Unresolved: Needs decision and/or implementation.
- Blocked: Requires an external dependency or policy decision.

### Validation & Confidence Policy

All rules for validation, error handling, invariants, and “confident programming” (no defensive checks, edge-only validation, smart constructors, CI gates) are defined in POLICY.md. Treat that document as binding; this file does not restate them.

### Build & Test Commands

- Use the repository `Makefile` for local automation. Invoke `make test`, `make lint`, `make ci`, or other documented targets instead of running ad-hoc tool commands.
- `make test` runs the canonical test suite for the active stack.
- `make lint` enforces linting rules before code review.
- `make ci` mirrors the GitHub Actions workflow and should pass locally before opening a PR.

## Tech Stack Guides

Stack-specific instructions now live in dedicated files. Apply the relevant guide alongside the shared policies above.

- Front-End (Browser ES Modules with Alpine.js): `AGENTS.FRONTEND.md`
- Backend (Go): `AGENTS.GO.md`
- Backend (Python): `AGENTS.PY.md`
- Docker and containerization: `AGENTS.DOCKER.md`
- Git and version control workflow: `AGENTS.GIT.md`
