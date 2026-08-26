# Two-Person Upskilling Program — Design Spec

**Date:** 2026-08-27
**Status:** Approved (design phase)
**Owners:** Thomas (coach + co-builder), Helena (primary builder)
**Repo:** `helenasaju71905-droid/My-Learning`
**Board:** "Version 2.0" — https://github.com/users/helenasaju71905-droid/projects/1

---

## 1. Purpose

A structured, evaluated upskilling program for **two learners** working on **one shared codebase** (the "Renewly" app), each with a distinct specialty and depth target. The program is gated: foundational skills (TypeScript + Linux) must be learned and **validated** before application building begins.

The repo doubles as a **learning-ops system**: plans, coding standards, a scoring tracker, and a Kanban board all live here, and progress is evaluated weekly with scores committed to `main`.

## 2. Learners, tracks, and depth

| Area | Helena | Thomas |
|---|---|---|
| Role | Primary builder (heavy lifting) | Coach + co-builder |
| TypeScript | Structured roadmap — foundational | Structured roadmap — foundational, applied to APIs + MCP |
| Linux | **Intermediate** (mostly embedded) | **Advanced** (embedded + deliberate drills) |
| Git | Learned by doing (not a class) | Already proficient |
| Core build | **DB + API** heavy lifting | Assists on simple API/DB tasks to learn TS |
| Specialty | **Automated QA — Playwright/TS** (SDET) | **MCP server + AI layer, from scratch in TS** |
| UI | Collaborative, Claude-designed | Collaborative, Claude-designed |

**Symmetry:** both go deep on a TypeScript specialty — Thomas on MCP/AI, Helena on test automation. Both get real API exposure (she builds it, he consumes it via MCP and assists on it).

## 3. Ground rules (revised from the original single-learner plan)

The original "she types every line, you never take the keyboard" rule is now **role-dependent**, because Thomas is also a builder:

- **On Helena's parts** (DB/API/QA): she types every line; Thomas reviews PRs, comments, requests changes — he does not fix them.
- **On Thomas's parts** (MCP/AI): he owns and builds them outright.
- **Shared:** commit daily (even 10 lines); 45-minute blocker rule (stuck 45 min → ask); one resource per topic, finish it (no tutorial-hopping); docs > videos after the foundations phase.
- **Scope freeze** at the end of the build phase, written into the README.

## 4. Program structure (Option A — strict gated)

Timeline assumes **~6 hrs/week per learner**.

| Phase | Focus | Branches | Gate to advance |
|---|---|---|---|
| **0 · Setup** (~1 wk) | Environment, accounts, repo/branch onboarding; Git-by-doing begins | `main` seeded by coach | Both can clone, branch, push, open a PR |
| **1 · Foundations** (~5–6 wks) | TS roadmap (structured) + Linux (Helena intermediate/embedded, Thomas advanced/drills); Git continues by doing | `helena/foundations`, `thomas/foundations` | **Validated:** ≥ 70% on foundations assessment (see §7) |
| **2 · Build Renewly** (~6–7 wks) | Helena: DB + API heavy lifting. Thomas: assist on simple API/DB + start MCP scaffolding vs stubs. UI collaborative | `feat/*` → `dev` | Skeleton + core CRUD working; PRs merged via review |
| **3 · Specialties** (~4 wks) | Helena: Playwright/TS suite (unit + integration + E2E). Thomas: MCP/AI layer over real `/reports/*` | `feat/*` → `dev` | Test suite green; MCP tools callable end-to-end |
| **4 · Ship** (~2 wks) | CI/CD, deploy, docs; interview prep (Helena) | `dev` → `main` | Live URL + README + final scoreboard |

**Total ≈ 18–20 weeks (~4.5 months).** If behind, cut features — never cut the testing phase.

## 5. Curriculum + reference materials

One resource per topic; finish it before moving on. Udemy links drift in price/content — pick the current, cheapest option when starting, then finish it.

### 5.1 TypeScript (both, structured)

| Stage | Topics | Resource |
|---|---|---|
| A. Fundamentals | types, functions, objects, unions, narrowing | [Total TypeScript — Beginner's Tutorial](https://www.totaltypescript.com/tutorials/beginners-typescript) (free) |
| B. Handbook depth | interfaces vs types, generics, `strict`, modules | [Official TS Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) |
| C. Applied | Zod, `Result<T,E>`, async, discriminated unions | [Total TypeScript free tutorials](https://www.totaltypescript.com/tutorials) + 12 practice programs |
| Checklist | overall skill map | [roadmap.sh/typescript](https://roadmap.sh/typescript) |

Deliverable: 12 practice programs green, `strict: true`, zero `any`, `/shared/schemas.ts` (Zod schemas for `Item`, `Renewal`, `User`, `Household`).

### 5.2 Linux

**Helena — intermediate:** [Linux Journey](https://linuxjourney.com/) (structured) + [The Linux Command Line (Shotts, free)](https://linuxcommand.org/tlcl.php) as reference. Navigation, files, pipes/grep, permissions, processes, ports/`lsof`, `apt`, nano — surfacing from running the stack.

**Thomas — advanced:** all the above **plus** [MIT Missing Semester](https://missing.csail.mit.edu/) (shell scripting/tooling) and [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) (CLI + security drills). Deeper: networking (`ss`, `tcpdump`), systemd basics, container internals, performance.

### 5.3 Git (by doing, not a class)

[Learn Git Branching](https://learngitbranching.js.org/) + [Oh My Git](https://ohmygit.org/) for onboarding; [Pro Git](https://git-scm.com/book) as lookup; [Conventional Commits](https://www.conventionalcommits.org/) for commit style. Learned live: branch → daily commit → PR → review → resolve a deliberate merge conflict (twice).

### 5.4 Specialty — Thomas (MCP/AI)

[MCP docs](https://modelcontextprotocol.io/) · [TS SDK](https://github.com/modelcontextprotocol/typescript-sdk) · [v2 SDK docs / 10-min server](https://ts.sdk.modelcontextprotocol.io/v2/) · [MCP Inspector](https://modelcontextprotocol.io/) for live tool testing · aggregated guide: [Scrimba — Best MCP Courses 2026](https://scrimba.com/articles/best-mcp-tutorials-and-courses/) · Udemy options: [MCP Crash Course](https://www.udemy.com/course/model-context-protocol/), [MCP Bootcamp](https://www.udemy.com/course/learn-mcp-model-context-protocol-course-and-a2a-bootcamphands-hands-on/), [topic page](https://www.udemy.com/topic/model-context-protocol-mcp/).

Design: **read-only** MCP server exposing the `/reports/*` endpoints as a **fixed toolset** (not text-to-SQL), reusing `/shared` Zod schemas as tool input schemas.

### 5.5 Specialty — Helena (Playwright/TS automation)

Docs: [Playwright](https://playwright.dev/docs/intro) · [POM](https://playwright.dev/docs/pom) · [Best practices](https://playwright.dev/docs/best-practices) · [VS Code extension](https://playwright.dev/docs/getting-started-vscode) · [Trace viewer](https://playwright.dev/docs/trace-viewer). Unit/integration: [Vitest](https://vitest.dev/) + [Supertest](https://github.com/ladjs/supertest). Video (free): [Playwright TS Full Course (YouTube)](https://www.youtube.com/watch?v=788GvvcfwTY). Udemy options: [Rahul Shetty — Playwright JS/TS](https://www.udemy.com/course/playwright-tutorials-automation-testing/) (also covers API testing, BDD, CI/CD, MCP), [Ultimate Guide + Framework](https://www.udemy.com/course/playwright-for-test-automation-the-ultimate-guide/), [Mastering Playwright with TS](https://www.udemy.com/course/mastering-playwright-test-automation-with-typescript/).

Test pyramid: ~20 unit / ~15 integration / ~8 E2E.

## 6. Repository layout (on `main`, owned by coach)

```
README.md                     ← public front page: what this is, tracks, links, live scoreboard snapshot, board link
docs/
  superpowers/specs/2026-08-27-upskilling-program-design.md   ← this spec
  plan/
    00-overview.md
    01-standards.md           ← coding standards, PR rules, definition-of-done, commit conventions
    02-roadmap-typescript.md
    03-roadmap-linux.md
    04-track-helena-qa.md
    05-track-thomas-mcp.md
    06-git-workflow.md
  tracker/
    scoreboard.md             ← weekly scores per learner
    rubric.md                 ← scoring definitions
  evaluation/
    weekly-eval.md            ← how evaluation runs (manual + scheduled)
```

## 7. Scoring & validation

**Weekly score** — 5 dimensions, 0–5 each (→ /25, shown as %):

| Dimension | Signal |
|---|---|
| Cadence | commit consistency (daily-ish), no long gaps |
| Correctness | runs / exercises pass / tests green |
| Quality | standards adherence, review-comment density |
| Understanding | can explain it (short quiz at phase ends) |
| Progress vs plan | on track for the phase |

**Validation gate (Phase 1 → 2):** each learner must score **≥ 70%** on a foundations assessment — TS exercises reviewed + Linux skills checklist demonstrated. No pass, no build phase.

## 8. Branch & board model

- **`main`** — coach-owned: plans, standards, tracker, README. Learners do not commit here.
- **`helena/foundations`, `thomas/foundations`** — Phase 1 individual learning branches.
- **`dev`** — integration branch for the build phases; `feat/*` branches PR into it.
- **`Plan`** — retired.

**Board "Version 2.0":** columns `Backlog → This Week → In Progress → In Review → Done`. Labels: `learner:helena|thomas`, `phase:0–4`, `track:ts|linux|git|api|qa|mcp|ui`. Phase 0–1 tasks seeded now; later phases seeded as reached.

## 9. Weekly evaluation mechanism

- **Scheduled remote agent (default):** a weekly cron routine running on Anthropic infrastructure (laptop can be off). It pulls the repo, reads each learner's branch, scores against §7, and commits the tracker + README scoreboard update to `main` and updates the board.
- **Manual trigger:** run on demand any time.
- **Constraint:** headless runs use git/GitHub over a stored token; anything needing an interactive local login is out of scope for the automated run.

## 10. The project — "Renewly" (shared build target)

Reminder app for things that expire (insurance, warranties, AMCs, doc expiry, subscriptions). Full data model, endpoints, and scope freeze are carried from the original plan and detailed in `docs/plan/04`/`05`. Key invariant retained: **`householdId` is derived from the authenticated session, never a request parameter.** The `/reports/*` endpoints are designed as narrow parameterized queries because they become Thomas's MCP tools ~1:1.

## 11. Out of scope (write into README at build phase)

Document/bill upload, OCR, mobile app, push notifications, multi-currency, public share links, tags, attachments, dark mode, i18n. The MCP/AI layer is in-scope for Thomas's track but built only after the core app validates.

## 12. Open follow-ups

- Verify write access to the "Version 2.0" board on first insert (it is Helena's user project; coach may need to be added as a project collaborator).
- Confirm exact weekly cron day/time for the scheduled evaluation.
