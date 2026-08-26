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

## What we sell · seven products

**Two tracks, and they do not sit on the same axis.** Five products serve a business
improving how it works. Two serve a founder building a venture. **A product is a product**
— how we build it is a separate question, further down.

### The matrix · five products for the customer-experience world

| | Product | What it is | Typical |
|---|---|---|---|
| **1** | **AI Agents**<br><sub>סוכני AI</sub> | An autonomous agent · takes input, does the work, returns output. Works 24/7 inside existing workflows. Single or multi-agent | ₪3K-30K per agent |
| **2** | **Smart Automations**<br><sub>אוטומציות חכמות</sub> | Workflow automation, cross-tool sync, scheduled jobs, with an intelligence layer. **Connects and sharpens without building a whole system** | ₪3K-25K |
| **3** | **Software Systems**<br><sub>מערכות תוכנה</sub> | A complete custom system · backend, database, UI, with AI at the core. **The data is the product** | ₪25K-100K |
| **4** | **Apps**<br><sub>אפליקציות</sub> | An end user **already in the client's world** — their customer, employee, supplier — doing things. **The experience is the product** | ₪20K-60K |
| **5** | **Sites**<br><sub>אתרים</sub> | Marketing presence, landing pages, content. **The UI, the message and the conversion are the product** | ₪3K-25K |

**Two pairs worth understanding.** *Agent ↔ Automation* is one world at two levels of
autonomy: an automation is cheap, fast and deterministic with an AI hook; an agent is
autonomous, expensive, and carries knowledge of its own. *Apps ↔ SaaS* is not a pair on
one axis at all — it is **the boundary between the two tracks.**

### The founder track · two products

Its audience is founders and people starting ventures, **not a business improving its own
operations.** Full transparency with clients: we invite founders into a partnership, we
do not present SaaS case studies we do not have.

| | Product | What it is | Typical |
|---|---|---|---|
| **6** | **MVP**<br><sub>השלב הראשון של מיזם</sub> | A technology partnership for a venture's first stage: from an idea to a **first product that actually works**, that real users can enter. **Not a Figma prototype, not a demo, not a spec** | ₪40K-120K · 2-3 months |
| **7** | **SaaS / AGaaS**<br><sub>מוצר תוכנה כעסק</sub> | Software sold as a service · **the software is the product** and the revenue comes from its use. End to end: the core, users, permissions, multi-tenant, subscriptions, billing, onboarding, admin, analytics, security | a business, not a project |

**AGaaS is the differentiator, and it is the direction the software world is going.**
Traditional SaaS gives a user tools to do the work. **AGaaS is a product where agents do
part of the work themselves, inside it** — noticing what needs attention, understanding
context, acting, and following through. A CRM gives you tools to handle leads; an AGaaS
product includes an agent that spots which lead needs attention, proposes the move, does
part of it, and keeps watching.

**MVP and SaaS are not a hierarchy.** A SaaS founder usually starts at MVP; an MVP can
equally lead to an app, a marketplace, a consumer product or an internal system. And a
SaaS client can arrive with a product that already exists.

### And every build carries the same envelope

A Studio workspace · full documentation and a runbook · walkthrough videos · a handover
pack · a support window at delivery · and a recommendation into ongoing Care.

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

### Coming, and the shape each one takes

| | | |
|---|---|---|
| **`agent-template`** | next | **A strong base with branches**, not one flat thing. The loop, the tools, the guardrails, the knowledge, the monitoring — then **voice**, **chat** and **task** on top. Three separate templates would mean three copies of the guardrails, and the guardrails are the part nobody may get wrong |
| **`automation-template`** | after | **Deliberately small.** An automation is almost never standalone, so it is mostly a characterization: is this around an agent we already built, or between third-party tools? **Both always attach somewhere** |
| **`saas-template`** | | `system` + `app`, **plus a layer neither half has**: many tenants, subscriptions, plans, entitlements, self-serve signup, metering. A SaaS is not a system with more users |
| **`mvp-template`** | | Real, **and temporary by design.** Fewer gates and a written debt list — with five never cut: auth, security, deploy, the legal minimum, QA |

> **And a capability that does not exist yet, named so it is not invented twice:**
> **promotion.** An MVP that found its market has to become production-grade — the cut
> gates get run and the debt list becomes the work-list. `bridge` joins surfaces,
> `adopt` takes in foreign code, and **neither promotes a build to a stricter
> template.** Until it exists, a person does it.

**When a spec lands on a template that is not built, say so** rather than bending a
neighbouring one into shape.

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
