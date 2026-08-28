# Claude Certified Architect — Foundations (CCA-F) · Study Plan

**Learner:** Helena · **Exam:** Sat 5 Sept 2026, 2:30 PM · **Commitment:** ~3 hrs/day · **Runway:** 7 study days

## Exam facts

| Spec | Detail |
|---|---|
| Format | 60 scenario-based questions, 120 min, closed-book, proctored (Pearson VUE), **no AI assistance** |
| Pass | 720 / 1000 scaled · $125 · valid 12 months |
| Style | Four scenarios from a bank of six — decision-making, favors the *simplest correct fix* |

## Domain blueprint (weight your hours to this)

| # | Domain | Weight | Watch-for |
|---|---|---|---|
| 1 | **Agentic Architecture & Orchestration** | **27%** | Most points lost here. The agentic loop: gather context → act → verify; task decomposition |
| 2 | Claude Code Configuration & Workflows | 20% | Claude Code fundamentals, CLAUDE.md hierarchy |
| 3 | Prompt Engineering & Structured Output | 20% | core + advanced prompting, structured output |
| 4 | Tool Design & MCP Integration | 18% | tool use, stop reasons (`tool_use` vs `end_turn`), MCP |
| 5 | Context Management & Reliability | 15% | context windows, reliability patterns |

## Strategy (mock-driven)

1. **Diagnostic first** — a cold, timed mock on Day 1 *before* studying, to expose weak domains. A low score is useful, not bad.
2. **Study from Anthropic's own docs** (it's closed-book on their material).
3. **Mocks are the engine** — review *every* wrong-or-guessed answer, map to a domain, re-drill.
4. **Reorder by weakness** — Days 2–5 get resequenced after the Day-1 diagnostic.
5. **Go/no-go gate:** ≥ **85% on a fresh timed mock** before Day 7 ends.

## 7-day schedule (Days 2–5 reorder after the diagnostic)

| Day | Date | Focus |
|---|---|---|
| — | Fri Aug 28 | Light: register for the exam, pick the Day-1 mock, skim the blueprint. No studying. |
| 1 | Sat Aug 29 | **Cold diagnostic mock** → fill `mock-01-diagnostic.md` → send Thomas the breakdown |
| 2 | Sun Aug 30 | Domain 1 — Agentic Architecture (27%) + quiz |
| 3 | Mon Aug 31 | Domain 2 — Claude Code & CLAUDE.md (20%) + quiz |
| 4 | Tue Sep 1 | Domain 3 — Prompt Engineering & Structured Output (20%) + quiz |
| 5 | Wed Sep 2 | Domain 4 — Tool Design & MCP (18%) + Domain 5 — Context Mgmt & Reliability (15%) + quiz |
| 6 | Thu Sep 3 | **Full timed mock #2** → review misses, map to domains, re-drill weakest |
| 7 | Fri Sep 4 | **Full timed mock #3** (final go/no-go, target ≥85%) + quick-reference review; rest early |
| — | Sat Sep 5 | Cheat-sheet skim in the morning; **exam 2:30 PM** |

## Resources

**Official (primary study source):**
- [Prompt engineering overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Tool use overview](https://docs.anthropic.com/en/docs/agents-and-tools/tool-use/overview)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Claude Code docs](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)

**Blueprint / guides:**
- [CCA-F exam guide & blueprint](https://claudecertificationguide.com/blog/claude-certified-architect-foundations-exam-guide)
- [freeCodeCamp prep](https://www.freecodecamp.org/news/claude-certified-architect-foundations-prep-for-anthropic-s-new-certification-exam/)
- [Community study guide (GitHub)](https://github.com/daronyondem/claude-architect-exam-guide)

**Mock exams:**
- [certificationpractice.com (free)](https://certificationpractice.com/practice-exams/anthropic-claude-certified-architect-foundations)
- [claudecertificationguide.com (free)](https://claudecertificationguide.com/)
- [FlashGenius](https://flashgenius.net/)
- [Udemy CCA-F masterclass](https://www.udemy.com/course/certified-claude-architect-masterclass-2026/)

## Tracking (daily commit on this branch)

- `mock-01-diagnostic.md` — Day-1 capture template (per-question, domain-tagged)
- `mock-scores.md` — mock % over time (the readiness signal)
- `progress-log.md` — daily entry: hours, topics, mock score, weak areas, tomorrow's focus
