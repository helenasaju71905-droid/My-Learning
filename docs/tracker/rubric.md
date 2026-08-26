# Scoring Rubric

Both learners are scored weekly by the coach (manual or scheduled — see [`../evaluation/weekly-eval.md`](../evaluation/weekly-eval.md)). Scores are recorded in [`scoreboard.md`](scoreboard.md) and snapshotted on the README.

## Weekly score — 5 dimensions, 0–5 each (→ /25, shown as %)

| Dimension | 0–1 | 3 | 5 |
|---|---|---|---|
| **Cadence** | few/no commits, long gaps | commits most days | daily commits, steady |
| **Correctness** | doesn't run / exercises fail | mostly works, minor gaps | runs clean / tests green |
| **Quality** | ignores standards, many review flags | mostly follows standards | clean, `strict`, zero `any`, few review comments |
| **Understanding** | can't explain choices | explains most | explains clearly, defends decisions |
| **Progress vs plan** | well behind | roughly on track | on/ahead of the phase plan |

Percentage = (sum / 25) × 100.

## Validation gate (Phase 1 → 2)

Each learner must score **≥ 70%** on a foundations assessment before the build phase:

- **TypeScript:** 12 practice programs green, `/shared/schemas.ts` complete, `strict: true`, zero `any` — reviewed by the coach.
- **Linux:** skills checklist demonstrated live — Helena to intermediate depth, Thomas to advanced (see [`../plan/03-roadmap-linux.md`](../plan/03-roadmap-linux.md)).

No pass, no build phase. This enforces "validate before building."

## Grade bands (for the weekly snapshot)

`≥ 85%` on track / strong · `70–84%` solid · `55–69%` needs attention · `< 55%` intervene (revisit the 45-min rule, resource fit, or hours).
