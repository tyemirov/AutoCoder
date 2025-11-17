# Contributing

Thanks for wanting to help! This repo is a collection of agent guardrails, so every change needs a little coordination before landing. Follow the steps below to make it easy for maintainers and reviewers from every ecosystem (Hack, PHP, Go, Python, etc.) to collaborate with you.

1. **Read the ground rules first.** Start with `CODE_OF_CONDUCT.md`, `AGENTS.md`, the relevant `AGENTS.*.md` stack guide, `NOTES.md`, and `POLICY.md`. They explain the validation expectations, testing philosophy, git workflow, and how we keep the workspace consistent.
2. **Pick an issue or create one.** Work flows through `ISSUES.md`. Append new issues as needed using the `[<ID>-<NUMBER>]` format, include a concise description, and note the stack you plan to touch. If you are bringing a new idea, open an issue before starting a big change so maintainers can build consensus.
3. **Plan before coding.** Draft `PLAN.md` (it’s ignored by git) with the steps you’ll take. Update it as you work; keep it accurate because reviewers rely on it when reading your PR.
4. **Branch with care.** Create branches named `feature/`, `bugfix/`, `improvement/`, `maintenance/`, or `blocked/` followed by the issue ID and short description (see `AGENTS.GIT.md`). Branch from the most recent issue branch or `master` when there isn’t one yet.
5. **Run the tooling.** Before changing files, run `make test`, `make lint`, and any stack-specific formatters noted in `AGENTS*`. After your edits, rerun the full suite (with the timeout wrapper described in `NOTES.md`) so that CI will pass when your PR lands.
6. **Document what changed.** Summarize the change inside `ISSUES.md` (mark `[x]` once tests pass and include a short note about the resolution). Update `CHANGELOG.md` if your change affects release notes, and mention any ecosystem-specific guidance for Hack, PHP, etc., when relevant.
7. **Submit your PR.** Push the branch to `origin`, open a PR with `gh pr create`, target the prior issue branch (or `master` for the first change), and link back to the issue. Mention the stacks you touched and any follow-up testing you expect.

If you plan to use the code commercially before 2026-11-17, see `LICENSE` and email `admin@mprlab.com` with your intended use so we can discuss a commercial license. After that date, the repo converts to MIT and no additional steps are required.
