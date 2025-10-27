# AutoCoder

AutoCoder is a set of techniques for leveraging autonomous coding agents.

This repository contains a set of files that can be dropped into a project to improve the automated workflow of coding agents.

## Assumptions

1. There is both a local and a remote repository (GitHub or similar).
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

### ISSUES.md example

```md
## BugFixes (300–399)

- [ ] [GN-300] Typing is sometimes blocked (can't type) or paste.  Unsure of the use case, seems haphazard. Review the code to see if you can find the potential cause
- [ ] [GN-302] A large space is left under the markdown notes from time to time. Ensure we are aware of the real height of the note and can measure the height needed. Check with MDE if the editor we use exposes an ability to measure the text's height
- [ ] [GN-303] The synchronization doesn't refresh. I just added a note on another device then logged in a computer where a session was already running and got no not there. When I opened the console I saw a lof of message about expired authentication.
- [ ] [GN-304] Clicking on a note starts it for editing (expected behavior) and places the cursor in the right place but it yanks the note to the top (unexpected behavior).
	- Solutions:
		- Center the whole scroll around the active card. Introduce a notion of a card being active, if not already. Consider active being last selected, e.g. the card stays immobile but the feed around it moves. So a card that finished editing doesnt move but all other cards moved underneath it. 
    - Effectively clicking on a card freezes it on the screen after moving it to the vewport. So if I click on a large renderedHTML view, I expect to get the rendered markdown view with the cursor in the place of my click, and no movement as the point of click was clearly in the view when I clicked on it
- [ ] [GN-305] I can still see scrollers ![scroller screenshot](scroller.png). There should be no scrollers in the makrdown view.
```
