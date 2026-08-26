# Coding Standards & Ways of Working

Applies to both learners on every branch. Adherence is scored (Quality dimension, see [`../tracker/rubric.md`](../tracker/rubric.md)).

## Ground rules

- **Role-dependent keyboard rule.** On Helena's parts (DB/API/QA) she types every line; Thomas reviews PRs and comments, he does not fix them. Thomas owns and builds his MCP/AI parts.
- **Commit daily**, even 10 lines. Cadence is a real recruiter signal and is scored.
- **45-minute blocker rule.** Stuck 45 min → ask. Not 4 hours, not 5 minutes.
- **One resource per topic, finish it.** No tutorial-hopping.
- **Docs > videos** after the foundations phase.
- **Scope freezes** at the start of the build phase — written into the README.

## TypeScript

- `"strict": true` always. **Zero `any`.**
- Banned: `enum` (use literal unions), `as` casting, decorators, namespaces, abstract classes.
- Validate all untrusted input with **Zod** at the boundary; infer types via `z.infer`.
- Money as **integer minor units**. Dates stored **UTC** (`timestamptz`), converted at the edge.

## Git & commits

- [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `docs:`, `test:`, `refactor:`.
- Feature branches; PR into `dev` (build phases) or work on `*/foundations` (Phase 1). `main` is coach-owned.
- `.gitignore`: `node_modules`, `.env`, `dist`, `*.log`. Commit `.env.example`, never `.env`.

## Definition of Done (a task/PR is done when)

1. Code compiles under `strict` with zero `any`.
2. Lint + typecheck pass.
3. Relevant tests exist and are green (build/specialty phases).
4. No secrets, no `console.log` debugging left in.
5. PR reviewed and approved (Helena's work reviewed by Thomas).
6. Board card moved to **Done**.

## Reviews

Thomas reviews Helena's PRs with real comments — naming, edge cases, missing validation, happy-path-only handling. He requests changes and lets her push again; he does not push fixes into her branch.
