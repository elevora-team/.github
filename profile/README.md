<div align="center">

# Elevora · Build System

**Four templates. One spine. Eight commands.**

*Every Elevora project carries its own instructions.*

</div>

---

## Start here

**New machine? Two lines, once.**

```bash
claude plugin marketplace add elevora-team/elevora-claude-plugins
claude plugin install elevora
```

> Inside a running Claude Code session, drop the `claude` prefix: `/plugin marketplace add …`
> **In a terminal, `/plugin` is not a program** — it returns `no such file or directory`.

Then read **[`dev-setup.md`](https://github.com/Elevorateam/elevora-teamplatform/blob/main/packages/knowledge/docs/delivery/dev-setup.md)** · twenty minutes, and you can open any Elevora repo and know the next move.

---

## The repositories

| | What it is | When you touch it |
|---|---|---|
| **[elevora-claude-plugins](https://github.com/elevora-team/elevora-claude-plugins)** | The plugin · `/elevora:adopt` + `/elevora:guide` | Install once per machine |
| **[site-template](https://github.com/elevora-team/site-template)** | Sites · marketing presence, the UI and the conversion are the product | A client needs a site |
| **[system-template](https://github.com/elevora-team/system-template)** | Software systems · backend + DB + UI. **The data is the product** | A client needs records and accounts |
| **[app-template](https://github.com/elevora-team/app-template)** | Apps · an icon installed from a store | Push, offline or store presence is a real requirement |
| **[monorepo-template](https://github.com/elevora-team/monorepo-template)** | The container · several products for one client | Two surfaces or more |

---

## Three situations, three commands

| You have | You type |
|---|---|
| **Nothing.** New client, blank page | `/elevora:start` |
| **Code already.** Someone handed it over, or you inherited it | `/elevora:adopt` |
| **One product, adding a second** | `/elevora:bridge` |

`/elevora:adopt` **reads, classifies, writes a plan, and stops.** Nothing moves until you read it and run `/elevora:adopt apply`.

---

## What a template carries

```
PLAYBOOK.md         the gate map · what each gate asks, and what it cost when nobody did
CHECKLIST.md        the same gates as tick boxes · the live state
build-profile.ts    the decisions · what, why, when, and what would reopen it
scripts/check.mjs   41 checks · exits non-zero when something is broken
BRIDGE.md           joining an existing build without duplicating a backend
SECURITY.md         where secrets live, and what to do when one leaks
```

**A gate is a question, not a task.** `AP0` asks *"which store does this ship to?"* — and the answer decides what gets built, what the checker asserts, and what may honestly be promised. **An unanswered gate does not close.**

**And the checker does not print a report — it exits with a status code.** So it blocks a commit, blocks CI, and refuses to close a gate.

> **A ticked box is a claim. The exit code is the fact.**

---

## The eight commands

| | |
|---|---|
| `/elevora:start` | New project · runs the characterization, forks the right template |
| `/elevora:adopt` | **Existing code** · classifies it, maps it on, adds the spine. Moves nothing on the first run |
| `/elevora:bridge` | Second product · joins the same backend, identity and brand |
| `/elevora:gate` | Runs and closes one gate |
| `/elevora:status` | Read-only · where the project stands. Touches nothing |
| `/elevora:gap` | Files what the template should have carried and did not |
| `/elevora:handover` | Closes out, strips our process, hands over |
| `/elevora:guide` | **The client's.** For whoever inherits code they did not write |

Two of them — `adopt` and `guide` — come from the plugin and work **in every folder on the machine**, including a repo that has never heard of us. The other six arrive with the template, because they are specific to it: `/elevora:gate AP6` means something in an app build and nothing in a site build.

---

## Works in any agent

**Almost none of this is Claude-specific, and the part that is, is only a shortcut.**

| Portable · runs anywhere | Claude Code only |
|---|---|
| `scripts/check.mjs` · plain Node, zero dependencies, **answers with an exit code** | The `/elevora:` shortcut |
| `AGENTS.md` · itself the cross-agent standard | The plugin that distributes two commands |
| `PLAYBOOK` · `CHECKLIST` · `GATE-0` · `BRIDGE` · `SECURITY` · `build-profile.ts` | |

The eight commands are **markdown files** at `.claude/commands/elevora/`. Another agent reads them the way it reads `AGENTS.md` — as instructions. Codex, Cursor, Antigravity: hand it the path, it does the identical work.

**And the rule that survives every agent:** a gate closes when `node scripts/check.mjs --gate <id>` exits 0 — never when an agent reports that it finished.

---

<div align="center">

**Private repositories.** If a clone fails with a permission error, that is org access missing — not a broken command.

<sub>© Elevora</sub>

</div>
