# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

This top-level repo is an umbrella: each project is a separate (currently private) repo included as a git submodule, so visibility is controlled per project. `backend/` and `infra/` are placeholders. The only project so far is the Android e-passport/eID reader at `frontend/apps/android/id-reader/` (submodule of `mandi-vrushi/id-reader-android`). Its `CLAUDE.md` (tracked as `Claude.md`) has the commands, architecture and security invariants. Run Gradle, `tools/` and project git commands from inside that directory.

This umbrella repo is **public** while the submodules are private. Anything committed here, including `.gitmodules` URLs and these docs, is world-readable, so don't put project details or secrets in it.

Submodule workflow:
- Clone with `git clone --recurse-submodules`, or run `git submodule update --init` after a plain clone.
- Committing and pushing inside a project doesn't update this repo. After pushing, commit the new submodule pointer here (`git add <path> && git commit`).
- `git submodule update` checks projects out on a detached HEAD. Run `git switch <branch>` inside the project before committing there.
