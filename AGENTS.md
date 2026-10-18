# Agent instructions

## Workspace layout

This repository is one folder in ~/Apps. See the workspace layout in
~/Apps/000-0-workspace/docs/workspace-layout.md.

CLAUDE.md and GEMINI.md are regular pointer files to AGENTS.md. Do not edit or replace them.

## Shared workspace policy

Read `~/Apps/000-0-workspace/docs/repository-protection.md` for delivery,
branches, external isolated worktrees, visibility, Git identity, and secrets. Read
`~/Apps/000-0-workspace/docs/agent-instruction-files.md` for pointer rules,
policy routing, owner decisions, unchecked claims, and shared conduct. Read
`~/Apps/000-0-workspace/docs/project-quality-checks.md` for the local baseline
and verification. Read `~/Apps/000-0-workspace/docs/update-and-development-tools.md`
before maintenance work, including retired-boundary rules. These references are
instructions to read. If required policy is missing, the affected task is
incomplete; do not clone, install, or reconstruct it.

## Source file

This repository is the only copy of the tmux cheat sheet.

Edit `README.md`. That file is the cheat sheet.

Do not create `~/Apps/tmux-cheat-sheet.md`.
Do not copy the sheet into `~/Apps`.

`~/Apps` is a workspace directory. It is not this repository.

## Work directory

Set the work directory to this repository before you edit files or run git:

```text
~/Apps/tmux-cheat-sheet
```

## License

This sheet uses CC BY-NC-SA 4.0. See `LICENSE`.

## Workflow review follow-up

`tmux -V` is the development-tool smoke probe. Do not use it as evidence that
a server, session, configuration or key binding works. Keep those checks in
this repository's user workflow. The unsupported generic probe was fixed
before the development-tools release and has a regression test.
