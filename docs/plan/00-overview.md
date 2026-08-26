# Program Overview

A gated, two-person upskilling program on one shared codebase (the **Renewly** app). Full design: [`../superpowers/specs/2026-08-27-upskilling-program-design.md`](../superpowers/specs/2026-08-27-upskilling-program-design.md).

## Learners

| | Helena | Thomas |
|---|---|---|
| Role | Primary builder (heavy lifting) | Coach + co-builder |
| TypeScript | Structured roadmap | Structured roadmap (applied to APIs + MCP) |
| Linux | Intermediate (embedded) | Advanced (embedded + drills) |
| Git | By doing | Already proficient |
| Core build | DB + API | Assists on simple API/DB tasks |
| Specialty | Playwright/TS automation (SDET) | MCP server + AI layer in TS |

## Pace & timeline

**~8 hrs/week per learner → ~14–15 weeks (~3.5 months).**

| Phase | Length | Focus |
|---|---|---|
| 0 · Setup | ~1 wk | Environment, repo/branch onboarding, Git-by-doing |
| 1 · Foundations | ~5 wks | TypeScript roadmap + Linux; **validation gate ≥ 70%** |
| 2 · Build Renewly | ~4.5–5.5 wks | DB + API + UI; Thomas begins MCP scaffolding |
| 3 · Specialties | ~3 wks | Playwright suite (Helena) + MCP/AI layer (Thomas) |
| 4 · Ship | ~1.5 wks | CI/CD, deploy, docs, interview prep |

If behind, cut features — never cut the testing phase.

## Documents

- [`01-standards.md`](01-standards.md) — coding standards, PR rules, definition-of-done
- [`02-roadmap-typescript.md`](02-roadmap-typescript.md) — daily TS push schedule
- [`03-roadmap-linux.md`](03-roadmap-linux.md) — Linux tiers + drills
- [`04-track-helena-qa.md`](04-track-helena-qa.md) — Helena's build + QA track
- [`05-track-thomas-mcp.md`](05-track-thomas-mcp.md) — Thomas's TS + MCP track
- [`06-git-workflow.md`](06-git-workflow.md) — branches, PRs, commits
- [`../tracker/rubric.md`](../tracker/rubric.md) · [`../tracker/scoreboard.md`](../tracker/scoreboard.md)
- [`../evaluation/weekly-eval.md`](../evaluation/weekly-eval.md)
