# tmux cheat sheet for agent sessions

Teaches basic tmux commands to keep AI agents running in separate terminal sessions, even after the terminal closes.

This sheet is for a person who is not a software developer. It teaches a few daily keys. It does not teach every tmux command.

## What tmux does

tmux keeps terminal work alive in the background.

You start a **session**. That session is a named workspace. Agent programs run inside it.

You can leave the session. The programs continue to run. You can return later and see the same work.

If you close the terminal window, or you lose the connection, tmux does not stop the agents. That is the reason to use tmux.

## The three layers

tmux has three layers. Learn the picture before you learn the keys.

```text
session  = a named workspace that stays alive
  window = one full-screen tab
    pane = a split of that tab (optional)
```

| tmux word | Think of it as | Best use |
|---|---|---|
| Session | A saved workspace | One group of agent work |
| Window | A tab | One agent, or one shell |
| Pane | A split view | Two related views at the same time |

Rule: give each agent its own window. Use a pane only when you need to see two things at once.

Look at the bar at the bottom of the screen. It shows the session name and the window names.

## The prefix: Ctrl-b

Most tmux shortcuts use two steps:

1. Press `Ctrl-b`. Then release both keys.
2. Press the action key.

This is not one combined key hold. `Ctrl-b` tells tmux that the next key is a tmux command.

This sheet writes that pattern as `Ctrl-b` then `c`.

If you forget a key, press `Ctrl-b` then `?`. Press `q` to close the help screen.

## Six keys for daily work

Learn these keys first. The rest of the sheet is optional.

| Goal | Keys |
|---|---|
| Create a new window | `Ctrl-b` then `c` |
| Next window | `Ctrl-b` then `n` |
| Previous window | `Ctrl-b` then `p` |
| Jump to window 0 to 9 | `Ctrl-b` then `0` ... `9` |
| Rename this window | `Ctrl-b` then `,` then type a name, then `Enter` |
| Leave. Keep the programs running | `Ctrl-b` then `d` |

## Start or return

Use one command. It creates the session `agents` if that session does not exist. It attaches if the session exists.

```bash
tmux new -A -s agents
```

Other useful commands from a normal shell (not inside tmux):

| Goal | Command |
|---|---|
| List sessions | `tmux ls` |
| Attach to `agents` | `tmux attach -t agents` |
| Stop session `agents` and every program in it | `tmux kill-session -t agents` |

CAUTION: `kill-session` stops every agent in that session. Use `Ctrl-b` then `d` when you want the agents to continue.

## Preferred agent commands

Start one agent in one window. Type the command. Then press `Enter`.

| Tool | Command |
|---|---|
| Hermes harness | `hermes` |
| Pi harness | `pi` |
| OpenAI Codex CLI | `codex` |
| Google Antigravity | `agy` |

Name the window after the agent. After you open the window, press `Ctrl-b` then `,`. Type `hermes`, `pi`, `codex`, or `agy`. Then press `Enter`.

## Everyday workflow

1. Start or return: `tmux new -A -s agents`
2. Create a window: `Ctrl-b` then `c`
3. Name the window: `Ctrl-b` then `,`
4. Start the agent: `hermes`, `pi`, `codex`, or `agy`
5. Switch windows: `Ctrl-b` then `n`, or `p`, or a number
6. Leave: `Ctrl-b` then `d`
7. Return later: `tmux new -A -s agents`

## Suggested layout

```text
agents session
├── hermes     main Hermes chat
├── pi         Pi chat
├── codex      OpenAI Codex CLI
├── agy        Google Antigravity
├── shell      normal shell for commands
└── notes      scratch text
```

Do not put two agents in the same window. Each agent needs a full screen. Two agents that edit the same files can conflict.

## Windows

| Goal | Keys |
|---|---|
| Create a new window | `Ctrl-b` then `c` |
| Close this window | `Ctrl-b` then `&`, then confirm |
| List windows and pick one | `Ctrl-b` then `w` |
| Switch to the last window | `Ctrl-b` then `l` |

You can also type `exit` in an empty shell to close that window.

## Read earlier output

Agent text can leave the visible area. To read earlier lines:

1. Press `Ctrl-b` then `[`
2. Use the arrow keys, `PageUp`, or `PageDown`
3. Press `q` to return to normal typing

## Panes (optional)

A pane splits one window into two terminals. Read this section after you can switch windows without help.

Use a pane to watch a log next to a shell. Do not use a pane for a second independent agent.

| Goal | Keys |
|---|---|
| Split left and right | `Ctrl-b` then `%` |
| Split top and bottom | `Ctrl-b` then `"` |
| Move to a pane | `Ctrl-b` then an arrow key |
| Make this pane full screen | `Ctrl-b` then `z` (same keys to restore) |
| Close this pane | `Ctrl-b` then `x`, then confirm |

## If something goes wrong

| Problem | What to do |
|---|---|
| `tmux ls` shows no session | No session is running. Run `tmux new -A -s agents`. |
| You closed the terminal and the agent is gone | You stopped the session. Next time, leave with `Ctrl-b` then `d`. |
| You see two status bars | You started tmux inside tmux. Press `Ctrl-b` then `d` to leave the inner session. |
| The agent does not accept `Shift+Enter` | See the Pi note in [Later commands](#later-commands). |

## Later commands

These are useful after you can use the daily keys without this sheet.

| Goal | Command |
|---|---|
| Rename the session | `tmux rename-session -t agents work` |
| Create a named window from a shell | `tmux new-window -t agents -n hermes 'hermes'` |

If `Shift+Enter` does not work in Pi inside tmux, add this to `~/.tmux.conf`. Then restart tmux:

```tmux
set -g extended-keys on
set -g extended-keys-format csi-u
```

The `extended-keys-format` option requires tmux 3.5 or later.

## Why this sheet is short

Beginner tmux guides agree on one teaching order:

1. Teach the three layers first. A session holds windows. A window holds panes. ([tmux wiki](https://github.com/tmux/tmux/wiki/Getting-Started), [Linux Handbook](https://linuxhandbook.com/tmux/))
2. Teach the prefix as two steps, not one combined key hold. Press `Ctrl-b`. Release. Then press the action key. ([Linux Handbook prefix lesson](https://linuxhandbook.com/courses/tmux/tmux-essential-shortcuts/))
3. Treat a session as a workspace that you join, not as extra tabs. ([Sebasblog tmux guide](https://sebasblog.com/p/the-ultimate-guide-to-tmux-supercharge-your-terminal-productivity/))
4. Put each agent in a named window. Do not start with a grid of panes.

This sheet follows that order. It hides shell recipes and extra keys until the daily path is stable.

## License

Copyright (c) 2026 tmux-cheat-sheet contributors.

This sheet uses [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). See [LICENSE](LICENSE).

The license permits you to copy, share, and adapt this sheet under these terms:

- You give appropriate credit and link to the license.
- You identify your changes.
- You do not use the sheet for commercial gain.
- You use the same license for adapted material.

This list is a summary. Read the license text for the complete terms.

The license applies to this sheet. It does not apply to programs that you write after you read the sheet.

## Notes and updates

| Date | Change |
|---|---|
| 2026-09-12 | Change the license from MIT to CC BY-NC-SA 4.0. |
| 2026-09-12 | Update the preferred-agent examples and public attribution. |
