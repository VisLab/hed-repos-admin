<!--
  COMMITTED AND PUBLIC, and the single source of instructions for every AI
  assistant working in this repo. Claude Code reads it through the @AGENTS.md
  import in CLAUDE.md; Copilot reads it directly.

  Write only what a reader needs going forward. No history: no dates, no "this
  was changed", no "used to", no rationale about superseded designs. If a fact
  is only interesting because of how the code got here, it belongs in
  .status/decisions.md, which is gitignored and is the place for that.

  Every line must be true on any machine and on Linux CI: no drive letters, no
  absolute paths, no secrets. Machine facts go in .status/local-environment.md.
  Target: under 200 lines.
-->

# hed-repos-admin

Coordination repository for the HED-related repositories while they are being standardized: the cross-repo map (`REPOS.md`) and, in the gitignored `.status/`, the working plans that span more than one repository. **This repo stores coordination documents only - no code.**

This repository belongs to no repo cluster and grants no standing access to any other repository - deliberately. A session launched here adds only the repositories that session is actually about; cross-repo material for a single cluster lives with that cluster, not here.

## Commands

Test framework: none. There is no code here, and there are no build, test, or lint commands. If that ever changes, this section changes in the same commit that changes it.

## Layout

- `REPOS.md` - the map: each repository, its one-line purpose, its cluster, what it owns, and what it depends on. The reason this repo exists; start here.
- `.status/` - working notes and the cross-repo plans. **Gitignored; local to each machine.**

## Conventions that differ from defaults

- **Markdown headers are sentence case** - capitalize the first word only, plus proper nouns and acronyms.
- **ASCII only** in prose and filenames: `-` not em/en dashes, `->` not arrows, `...` not an ellipsis character, straight quotes, and `|--` rather than box-drawing characters in tree diagrams. The exception is genuine data: author names and dataset titles keep whatever characters they contain.
- **Committed files carry no project history.** No dates, no "this was changed", no phase or session labels. Rationale about how things got here goes in `.status/decisions.md`.
- **Nothing that ships may reference `.status/`.** It is gitignored, so such a pointer is a dead link for every reader but its author. The exception is the files whose job is to orient a tool - this file, `CLAUDE.md`, `.gitignore`, the files under `.claude/` (`settings.json`, `rules/`), and those under `.github/` (`copilot-instructions.md`, `instructions/`) - which may name `.status/` paths as places to look.
- **No committed file contains a local path or a drive letter.** Those go in `.status/local-environment.md`. This repo is public.
- **Repositories are referred to by name, never by path** - in `REPOS.md` and everywhere else committed.
- **Line endings are LF.** `.gitattributes` (`* text=auto eol=lf`) enforces this at commit time.

## Related repositories

`REPOS.md` is the full map. The one every session here needs:

- `hed-metadata-toolkit` - the finished reference example of the standardized layout (AGENTS.md as single instruction source, committed settings, the `.status/` conventions).

## Where the thinking lives

`.status/` is gitignored, so it exists only on the machine that wrote it and never in a fresh clone or worktree.

- `.status/README.md` - the index. Read this first; it lists what is active.
- `.status/decisions.md` - why things are the way they are, and the home for anything historical. Read before proposing structural changes. Append entries; never rewrite one.
- `.status/plans/*.md` - active plans, including the cross-repo standardization plan. Check the `Status:` header and the `[ ]` / `[x]` markers before starting work.
- `.status/notes/*.md` - dated records of what happened. Write-once reference material, not instructions.
- `.status/local-environment.md` - this machine's paths and quirks. Tool-agnostic, because more than one assistant works here. Never copy its contents into a committed file.
- IMPORTANT: do not read `.status/archive/` unless a file is named for you. Nothing new is created at the `.status/` root - new material goes in `plans/`, `prompts/`, `notes/`, or `scratch/`.

## Working agreements

- **IMPORTANT: every file written to `.status/` opens with a `For humans:` summary.** Three or four sentences, at the very top, before any other heading: what this file is, and the one or two things a person needs to take away from it. Write it plainly - no throat-clearing, no restating the title. The same applies to a long answer in a session: lead with the conclusion.
- IMPORTANT: never delete or rewrite a file under `.status/` without asking first. Appending is fine.
- IMPORTANT: temporary scripts, experiments, and one-off files go in `.status/scratch/` - never the repository root. Anything in `scratch/` may be deleted unread.
- Show evidence, not assertions: the command you ran and its actual output.
- For a change spanning more than three files, write a plan to `.status/plans/` and stop for review before editing.
- Do not commit, push, or create branches unless asked.
