# Weekly Evaluation

How progress gets scored and recorded each week.

## Schedule

- **Default (automated):** a scheduled remote agent runs **Sundays 11:00 AM IST (05:30 UTC)** on Anthropic infrastructure — **the coach's laptop can be off.**
- **Manual:** the coach can trigger an evaluation on demand at any time ("run the weekly eval").

## What the evaluation does

1. Pull the repo; read commits on each learner's active branch (`*/foundations` in Phase 1, `feat/*` + `dev` later) since the last evaluation.
2. Assess against the 5 rubric dimensions (see [`../tracker/rubric.md`](../tracker/rubric.md)): cadence, correctness, quality, understanding, progress vs plan.
3. Append a scored row per learner to [`../tracker/scoreboard.md`](../tracker/scoreboard.md).
4. Refresh the **scoreboard snapshot on the README**.
5. Update the **"Version 2.0" board** — move completed cards to Done, flag stalled ones.
6. Commit and push all of the above to `main`.

## Constraints

- Headless runs operate over **git/GitHub with a stored token** — this is what works without the coach present.
- Anything needing an interactive local login is out of scope for the automated run; do it in a manual eval.
- At phase boundaries the eval also records the **validation-gate result** in the scoreboard's gate log (understanding is confirmed via a short live check by the coach, not automated).

## Output each week

- Two scored scoreboard rows (Helena, Thomas) + updated README snapshot.
- A short written note per learner: what went well, what to fix, whether they're on track for the phase.
