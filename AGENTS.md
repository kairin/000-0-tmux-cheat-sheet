# Agent instructions

## Workspace layout (read first)

This repository is one of three that must exist in `~/Apps`. An agent that reads this file must make sure all three clones are present before other work.

| Path | Remote |
|---|---|
| `~/Apps/000-dotfiles` | `https://github.com/kairin/000-dotfiles.git` |
| `~/Apps/ASD-STE100` | `https://github.com/kairin/ASD-STE100.git` |
| `~/Apps/tmux-cheat-sheet` | `https://github.com/kairin/tmux-cheat-sheet.git` |

`~/Apps` is a workspace directory. It is not a git repository.

Before any other work:

1. Make sure each path exists and is a git clone.
2. If a path does not exist, clone it from the remote in the table.
3. If `~/Apps/000-dotfiles` exists, run `~/Apps/000-dotfiles/scripts/ensure-workspace-layout.sh`.
4. If `000-dotfiles` does not exist, clone it first. Then run the command.

The script creates `~/Apps/AGENTS.md` and `~/Apps/GEMINI.md` as symlinks to `~/Apps/000-dotfiles/AGENTS.md`.

`GEMINI.md` in this repository is a compatibility symlink to this file.

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

## Git identity

Commit as `Mister K <678459+kairin@users.noreply.github.com>`. This is the
public GitHub name and the GitHub noreply email. Do not commit with another
name or with a personal email address. Check with `git config user.name` and
`git config user.email` before you commit.
