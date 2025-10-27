# AutoCoder

AutoCoder is a set of techniques for leveraging autonomous coding agents.

This repository contains a set of files that can be dropped into a project to improve the automated workflow of coding agents.

## Assumptions

1. There is both a local and a remote repository (GitHub or similar).
2. As of 10/26/2025, the sufficiently powerful autonomous agents are [Gemini CLI](https://github.com/google-gemini/gemini-cli), [Codex CLI](https://developers.openai.com/codex/cli/), and [Claude Code](https://github.com/anthropics/claude-code). One or more of these can be used for autonomous coding.
3. The repository follows standard coding practices, such as maintaining a `.gitignore`, a `CHANGELOG.md`, and a comprehensive `README.md`.

## Human Flow

1. Add [AGENTS.md](./AGENTS.md), [ISSUES.md](./ISSUES.md), [NOTES.md](./NOTES.md), and [POLICY.md](./POLICY.md) to your repository.
2. Add `PLAN.md` to `.gitignore`:  
```shell
   printf "\nPLAN.md\n" >> .gitignore
```

3. Decide on a short ID for your repository (e.g., `GX` for GIX or `AW` for Allergy Wheel).
4. Populate `ISSUES.md` with issues in the format `- [ ] [<ID>-<NUMBER>]`. Describe each issue in sufficient detail for a mid-level engineer to solve.
5. Run the coding agent and prompt it with:
```
Read NOTES.md and work on ISSUES starting with bugs. Work autonomously.
```
