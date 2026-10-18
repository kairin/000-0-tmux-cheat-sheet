# Next steps

## agy round 2 checklist (2026-10-18)

This checklist is the working copy of the round 2 tasks for `000-0-tmux-cheat-sheet`. The [round 2 review](../000-0-workspace/docs/core-agy-review-round2-2026-10-18.md#000-0-tmux-cheat-sheet) gives the evidence, and the [decision record](../000-0-workspace/docs/core-agy-decisions-2026-10-18.md) gives the reasons for the decided items. Where an earlier status in this file disagrees with this section, use this section.

### Status

"Ruled now" is the verified status. "Target" is the status after every task below passes on this host, before any delivery.

| Task | Ruled now | Target |
|---|---|---|
| TM-01 | accepted | accepted (unchanged) |
| TM-02 | accepted | accepted (unchanged) |

### Why round 1 failed here

Every task in this repository was ruled CORRECT or BLOCKED-CORRECT. Only the evidence corrections below remain.

### Do not delete or overwrite

- In every repository: Git branches, tags, stashes, reflog, untracked and ignored files. Do not run `git reset --hard`, `git clean`, a force push or a branch delete. Do not delete a dated receipt or a historical document.
- In `000-0-tmux-cheat-sheet`: Dated receipts, historical reviews, ledger history and evidence entries. Do not use a deletion quota to shorten a document.
- Allowed deletion in `000-0-tmux-cheat-sheet`: Text that an item explicitly replaces.

Apply the six delete rules of the [preservation contract](../000-0-workspace/docs/core-agy-review-round2-2026-10-18.md#preservation-contract-what-you-must-not-delete-or-overwrite) to every delete, move or replace operation.

### Tasks

Do the tasks from top to bottom. Each line gives: ID | parent or source | priority | files | what to do | acceptance check with its negative case | depends on. Tick a box only after its acceptance check passes and you have recorded the real command and exit code.

- [ ] **TM-LEDGER.R1** | TM-01/02 | P2 | ledger | Re-pin HEAD fa372360 + dirty (AGENTS.md, NEXT-STEPS.md, README.md); fix "AGENTS.md:29" -> :41; 26 -> 25 links or state the autolink is counted; add the link-check command and the repeated-text method (290->253 lines; 51->4). | Clean. | none
- [ ] **TM-02.R1** | TM-02 | P3 | NEXT-STEPS.md | State whether the 2026-10-07 T14 follow-up is closed; trim lines 6-7 duplicate link list. | Lint <= 2.5. | none

**Status:** to do.

This repository has follow-up work from the review of 2026-10-07 (task T14).
The owner keeps the full instructions in private notes, because they contain
local paths. Ask the owner for them before you start.

When the work is done, delete this file.
