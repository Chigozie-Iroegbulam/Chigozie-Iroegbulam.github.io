# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

This is the GitHub Pages user site: the home page that links all of the user's browser games. It's
live at https://chigozie-iroegbulam.github.io/ (served from `main`, root), and every push to `main`
redeploys it. It's a single static `index.html` (inline CSS, no build step) plus card images in `img/`.

## Required: commit and push your work to GitHub as you go

The goal is to never lose work or the current state of the project. Every working version must be
saved in Git and on GitHub so it's easy to go back to.

- **Commit while you work, not just at the end.** Each time you finish a logical piece of work (a
  new game card, a fix, a style change, a docs change), check it works, commit it, and push it before
  starting the next piece. Don't wait for the user to ask.
- **Never finish a task or end a session with uncommitted or unpushed changes.** Before reporting
  that you're done, run `git status -sb`. It must show a clean tree with `main...origin/main` and
  nothing ahead. If a push fails, say so and fix it. Don't call work saved until it has been pushed.
- **Clean commit messages:** an imperative summary line of 60 characters or fewer (e.g. "Add
  Snake game card"), a blank line, then a short body when the why isn't obvious. One logical change
  per commit. No vague "updates" or "WIP" commits.
- **Only commit working pages.** Any commit should be safe to go back to.
- **Undo with `git revert`, never by rewriting history.** No force-pushes, no `reset --hard` on
  pushed commits, no amending pushed commits.
- Remote: `origin` → `Chigozie-Iroegbulam/Chigozie-Iroegbulam.github.io` (public), branch `main`.

## How it fits together

Each game is its own repo with Pages turned on, so it's served under this domain at `/<repo-name>/`
(e.g. `/pixel-siege/`, `/tic-tac-toe/`). That's why the card links are relative paths. They work on
the live site but not when you open `index.html` from `file://`.

**Adding a game:** publish its repo with Pages on, then add an `<li class="game">` card to
`index.html` (thumbnail, title link, one-line description, tags, source link) and add a row to the
README table.

**Card images:** square JPEGs in `img/` (about 450–600px), taken as headless Chrome screenshots and
cropped with `sips`. Show the game mid-play where possible. Headless Chrome's minimum viewport is
500px wide, so narrower screenshots look clipped on the right.
