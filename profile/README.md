<div align="center">

# Elevora

### We build AI-first businesses.

**A company building custom AI solutions for the customer-experience world.**

We build internal AI systems, agents and automations that remove manual work and
streamline how businesses serve their clients · delivered through our Studio platform ·
improved through ongoing Care.

<sub>מכניסים את ה-AI לליבת העסק · מפתרון אחד, ועד מערכת שלמה.</sub>

</div>

---

## What we build

**Five product lines and a founder track.** A client can start with one and grow into a
whole operating system — that is the shape of the business, not an upsell.

| | Product | What it is |
|---|---|---|
| **1** | **AI Agents** · סוכני AI | Autonomous agents, single-purpose or multi-agent, working 24/7 inside existing workflows. **The autonomous end of the connected world** |
| **2** | **Smart Automations** · אוטומציות חכמות | Workflow automation, cross-tool sync, scheduled jobs, with an intelligence layer. **The simple, reliable end** — cheaper, faster, deterministic |
| **3** | **Software Systems** · מערכות תוכנה | Custom backends, CRMs, dashboards, internal tools, customer portals — with AI at the core. **The data is the product** |
| **4** | **Apps** · אפליקציות | An end user already in the client's world — their customer, their employee, their supplier — doing things. **The experience is the product** |
| **5** | **Sites** · אתרים | Marketing presence, landing pages, content. **The UI, the message and the conversion are the product** |

**And beside the matrix, the founder track:** **MVP** (a mode, not a template — the same
build with fewer gates and a written debt list) and **SaaS** (a composition — a system
and an app on one backend, one brand, one container).

**Every build ships with a Studio workspace**, full documentation, and the option of
ongoing Care.

---

## The working environment

**This organization holds the build system** — the templates, the checks and the commands
that carry how Elevora builds. Client work lives elsewhere; this is the machinery.

> **Every Elevora project carries its own instructions.** So an agent, a teammate or a
> new machine can open a project and know the next move without asking anyone.

### Start here · new machine, once

```bash
claude plugin marketplace add elevora-team/elevora-claude-plugins
claude plugin install elevora
```

**Not on Claude Code?** Codex, Cursor, Antigravity — the commands are plain files:

```bash
git clone --depth 1 https://github.com/elevora-team/elevora-claude-plugins /tmp/elevora
bash /tmp/elevora/install.sh
# then, in any agent:  "read ~/.elevora/commands/adopt.md and follow it in this repo"
```

> ⚠️ `/plugin` inside a terminal returns `no such file or directory` — a slash command is
> not a program. The terminal form above is written first for exactly that reason.

Then read **[`dev-setup.md`](https://github.com/Elevorateam/elevora-teamplatform/blob/main/packages/knowledge/docs/delivery/dev-setup.md)** · twenty minutes, and you can open any Elevora repo and know what to do.

---

## The repositories

| | What it is | When you touch it |
|---|---|---|
| **[elevora-claude-plugins](https://github.com/elevora-team/elevora-claude-plugins)** | The bootstrap · `/elevora:adopt` + `/elevora:guide` | Install once per machine |
| **[site-template](https://github.com/elevora-team/site-template)** | Sites | `SI0-SI14` |
| **[system-template](https://github.com/elevora-team/system-template)** | Software systems | `SY0-SY14` |
| **[app-template](https://github.com/elevora-team/app-template)** | Apps · an icon installed from a store | `AP0-AP14` |
| **[monorepo-template](https://github.com/elevora-team/monorepo-template)** | The container · several products for one client | `MR0-MR15` |

`agent-template` and `automation-template` are **not built yet.** When a spec lands on
one of them, say so rather than bending a neighbouring template into shape.

---

## Three situations, three commands

| You have | You run |
|---|---|
| **Nothing.** New client, blank page | `/elevora:start` |
| **Code already.** Handed over, or inherited | `/elevora:adopt` |
| **A container, and a foreign repo joining it** | `/elevora:adopt <repo-url>` |
| **One product, adding a second** | `/elevora:bridge` |

**`/elevora:adopt` reads, classifies, writes a plan, and stops.** Nothing moves until you
read the plan and run `/elevora:adopt apply`.

**And the question before the mechanics:** adopt a repo when it holds value that cannot
be recreated — years of history, accumulated SEO, a codebase that took months. **Two
weeks old and basic? Rebuild it from the right template and carry the content across.**

---

## The eight commands

| | |
|---|---|
| `/elevora:start` | New project · runs the characterization, forks the right template |
| `/elevora:adopt` | **Existing code** · classifies, maps it on, adds the spine. Moves nothing on the first run |
| `/elevora:bridge` | Second product · joins the same backend, identity and brand |
| `/elevora:gate` | Runs and closes one gate |
| `/elevora:status` | Read-only · where the project stands. Touches nothing |
| `/elevora:gap` | `push` sends a lesson up to the template · `pull` brings improvements down to an old project |
| `/elevora:handover` | Closes out, strips our process, hands over |
| `/elevora:guide` | **The client's.** For whoever inherits code they did not write |

Two of them — `adopt` and `guide` — work **in every folder on any machine**, including a
repo that has never heard of us. The other six arrive with the template, because they are
specific to it: `/elevora:gate AP6` means something in an app build and nothing in a site
build.

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

**A gate is a question, not a task.** `AP0` asks *"which store does this ship to?"* — and
the answer decides what gets built, what the checker asserts, and what may honestly be
promised. **An unanswered gate does not close.**

**The checker does not print a report — it exits with a status code.** So it blocks a
commit, blocks CI, and refuses to close a gate.

> **A ticked box is a claim. The exit code is the fact.**

---

## Works in any agent

| Portable · runs anywhere | Claude Code only |
|---|---|
| `scripts/check.mjs` · plain Node, zero dependencies, **answers with an exit code** | The `/elevora:` shortcut |
| `AGENTS.md` · itself the cross-agent standard | The plugin, as one delivery route |
| `PLAYBOOK` · `CHECKLIST` · `GATE-0` · `BRIDGE` · `SECURITY` · `build-profile.ts` | |

The commands are markdown files at `.claude/commands/elevora/`. Another agent reads them
the way it reads `AGENTS.md`. **The file is the command; the shortcut is a convenience
over it.**

**And the rule that survives every agent:** a gate closes when
`node scripts/check.mjs --gate <id>` exits 0 — never when an agent reports that it
finished.

---

<div align="center">

**Private repositories.** A clone failing with a permission error is org access missing, not a broken command.

<sub>© Elevora · <a href="https://elevora.co.il">elevora.co.il</a></sub>

</div>
