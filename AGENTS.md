# Agent instructions

## Workspace layout

This repository is one folder in ~/Apps. See the workspace layout in
~/Apps/000-0-workspace/docs/workspace-layout.md.

CLAUDE.md and GEMINI.md are regular pointer files to AGENTS.md. Do not edit or replace them.

## Secrets

The secret rules of the workspace apply only to real secret values: a real key, token, password or credential. Documentation that tells how to make, store or use a credential is not a secret. A placeholder such as `<REDACTED>` or `PASTE-TOKEN-HERE` is not a secret. Report a secret problem only when you find a real value. Do not report placeholders or setup steps as secret problems.

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

## Owner decisions and unchecked claims

- The owner's stated decision beats a general rule. Before you flag
  something, check whether the owner already decided on it (repository
  docs, AGENTS.md, earlier instructions). If they did, do not flag it again.
- Check a claim yourself before acting on it, above all a claim from an
  earlier session, a subagent or a report. Look at the file, image or data.
- Do only what was asked. Do not add new "outstanding issues" to a task, and
  do not raise again one the owner dismissed.
- Never propose deleting, purging or unpublishing anything because of a claim
  you have not checked yourself.

## Git identity

Commit as `Mister K <678459+kairin@users.noreply.github.com>`. This is the
public GitHub name and the GitHub noreply email. Do not commit with another
name or with a personal email address. Check with `git config user.name` and
`git config user.email` before you commit.
