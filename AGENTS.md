## Security, secrets, and TypeSafe AI

- Never expose, print, log, commit, or include in diffs, prompts, fixtures, screenshots, or generated artifacts any API key, token, password, credential, private key, session cookie, or other secret. Redact secrets from diagnostics and examples; use placeholders such as `<REDACTED>`.
- Never ask the user to paste a secret into chat. Do not read or display secret-file contents. If a required credential is unavailable, stop and explain how to provide it securely.
- TypeSafe authentication uses `TYPESAFE_API_KEY`, supplied only through the runtime environment or an approved secret manager. The user's local token source is `/home/kkk/.dotfiles/.typesafe.ai/api.token`; do not copy it into this repository, its `.env`/`.envrc`, source code, config, or documentation. Do not assume the variable is available; check presence without printing its value.
- Keep TypeSafe API calls server-side. Never expose `TYPESAFE_API_KEY` to browser/client bundles, public endpoints, or untrusted subprocesses. Do not send sensitive or personal data to TypeSafe unless the user explicitly authorizes that use and the project’s data-handling rules allow it.
- When a task involves TypeSafe, load and follow the installed `typesafe-ai` skill. Consult the live documentation index at https://docs.typesafe.ai/llms.txt and the task-relevant current API/SDK page or cookbook before implementation; do not invent request fields, response shapes, or SDK behavior. Treat skill guidance as a map, not a replacement for current docs.
- Review TypeSafe questions, criteria, thresholds, and uncertainty handling as application logic; validate representative cases and actual behavior. Keep these constants reviewable in one appropriate project location.

---

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
