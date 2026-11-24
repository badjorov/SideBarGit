# CLAUDE.md

This file guides Claude Code when working in this repository.

## What this project is

A **fork** of Tito Bouzout's *SideBarGit*, a Sublime Text 3 package that adds
git commands (add, commit, push, diff, log, blame, etc.) to the right-click menu
of the side bar and of open documents. The last upstream commit in this fork is
from February 2014. Nikolay has made no changes of his own. Upstream:
https://github.com/titoBouzout/SideBarGit

## Tech stack

- Python (Sublime Text 3 plugin API: `sublime`, `sublime_plugin`).
- Sublime config files: `*.sublime-menu`, `*.sublime-commands`,
  `*.sublime-keymap`, `SideBarGit.sublime-settings`.
- Shells out to the `git` command-line tool.

## How it is deployed

Not deployed from here. The upstream README says to install via Package
Control, not manually. To try this fork, copy the folder into Sublime Text's
`Packages/` directory.

## File structure

- `SideBarGitCommands.py` — all menu commands.
- `StatusBarBranch.py` — shows the current branch in the status bar.
- `sidebar/` — helpers: `SideBarGit.py` (runs git), `SideBarItem.py`,
  `SideBarSelection.py`, `SideBarProject.py`.
- `Side Bar.sublime-menu`, `Context.sublime-menu`, `Main.sublime-menu`,
  `Commands.sublime-commands`, `Default (*).sublime-keymap` — UI wiring.
- `SideBarGitGutterDiff.txt`, `license.txt`, `readme.md`.

## Risky areas

- Commands run real git operations (commit, `reset --soft HEAD~1`, amend,
  push) on the user's repositories. A bug here can change another repo.
- 2014-era code for Sublime Text 3; it may not work on Sublime Text 4 without
  changes.
- The license (`license.txt`) belongs to the original author. Keep it.

## Live vs. test copy

- Nothing is live. The default branch is `st3` (there is no `main`).
- Test any change in a throwaway git repo, never in a real project.

## Google Apps Script

None in this project.
