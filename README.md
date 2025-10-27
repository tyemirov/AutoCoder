# AutoCoder

AutoCoder is a set of techniques for leveraging autonomous coding agents.

This repository contains files that can be dropped into a project to improve the automated workflow of coding agents. It builds guardrails and techniques to produce meaningful, confident code, and to avoid “AI slop.”

![coding agents](GIS%20typing.png)

## Assumptions

1. Both a local and a remote repository exist (GitHub or similar).
2. As of 10/26/2025, the sufficiently powerful autonomous agents are [Gemini CLI](https://github.com/google-gemini/gemini-cli), [Codex CLI](https://developers.openai.com/codex/cli/), and [Claude Code](https://github.com/anthropics/claude-code). One or more of these can be used for autonomous coding.
3. The repository follows standard coding practices, such as maintaining a `.gitignore`, a `CHANGELOG.md`, and a comprehensive `README.md`.

## Human Flow

1. Add [AGENTS.md](./AGENTS.md), [ISSUES.md](./ISSUES.md), [NOTES.md](./NOTES.md), and [POLICY.md](./POLICY.md) to your repository. Replace angular bracketed placeholders with real values.
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

## Personal Observations of Coding Agents

### Claude Code

**Pros**

* Most responsive and warm personality.
* Fast execution speed.

**Cons**

* Coding skills are subpar in both backend and front-end compared to Codex.

*Conclusion* (as of 10/27/2025): use Codex, or create extra guardrails and smaller tasks for Claude.

### Gemini CLI

**Pros**

* Very fast.

**Cons**

* Does not follow instructions reliably.
* May perform large, irrevocable changes if left unchecked.

*Conclusion* (as of 10/27/2025): do not use Gemini CLI; not ready for daily use.

### Codex CLI

**Pros**

* Can autonomously work on large tasks.
* Decent understanding of the code base.
* Relentless in delivering results.

**Cons**

* Slow.
* Account usage runs out faster than stated.
* Uneven performance across models: the medium model can work well, while the high model may stumble.

*Conclusion* (as of 10/27/2025): use Codex CLI with the High model through API; treat it as an employee that needs guidance.

---

## ISSUES.md Example

```md
## BugFixes (300–399)

- [ ] [GN-300] Typing is sometimes blocked (can’t type or paste). The use case is unclear; it seems haphazard. Review the code to identify potential causes.
- [ ] [GN-302] A large space occasionally appears under markdown notes. Ensure the note’s real height is detected and the required height is measured. Check whether MDE or the editor exposes text height measurement.
- [ ] [GN-303] Synchronization doesn’t refresh. I added a note on another device, then logged into a computer with an already running session, and the note didn’t appear. In the console, I saw many messages about expired authentication.
- [ ] [GN-304] Clicking on a note correctly enters edit mode and places the cursor, but unexpectedly yanks the note to the top.
  - **Solutions:**
    - Center the scroll around the active card. Introduce a notion of an active card (e.g., last selected). When editing ends, the card should stay fixed while others move underneath.  
    - Effectively, clicking on a card freezes it in the viewport. For example, if I click on a large rendered HTML view, I expect to get the rendered markdown view with the cursor placed at my click, without any movement (since the click point was already in view).
- [ ] [GN-305] Scrollers are still visible ![scroller screenshot](scroller.png). There should be no scrollers in the markdown view.
```

