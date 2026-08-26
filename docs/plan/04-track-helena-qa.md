# Helena — Build + QA Track

Helena does the **heavy lifting** on the shared app (DB + API), then goes deep on **test automation** — her SDET specialty.

## Phase 2 — Build (DB + API)

Layering (kept simple):

```
routes/       →  HTTP only: parse, call service, send response
services/     →  business logic, no req/res objects
repositories/ →  data access (arrays first, then Prisma)
middleware/   →  errors, logging, auth
```

- Build `/api` with **in-memory arrays first** (isolates HTTP from ORM concepts), then swap the repository layer to **Prisma + Postgres** — routes/services shouldn't change (the payoff of layering).
- Zod validation at the boundary; central error handler + `AppError` with `statusCode`; structured logging with `pino`.
- Pagination, filtering, sorting on `GET /items`. `GET /health`.
- **`householdId` is derived from the session, never a request parameter.**
- Every route exercised in a committed [Bruno](https://www.usebruno.com/) collection.

## Phase 3 — Specialty: Playwright/TS

Docs: [Playwright](https://playwright.dev/docs/intro) · [Page Object Model](https://playwright.dev/docs/pom) · [Best practices](https://playwright.dev/docs/best-practices) · [VS Code extension](https://playwright.dev/docs/getting-started-vscode) · [Trace viewer](https://playwright.dev/docs/trace-viewer). Unit/integration: [Vitest](https://vitest.dev/) + [Supertest](https://github.com/ladjs/supertest).

Video (free): [Playwright TS Full Course (YouTube)](https://www.youtube.com/watch?v=788GvvcfwTY).
Udemy (pick one, current & cheapest): [Rahul Shetty — Playwright JS/TS](https://www.udemy.com/course/playwright-tutorials-automation-testing/) · [Ultimate Guide + Framework](https://www.udemy.com/course/playwright-for-test-automation-the-ultimate-guide/) · [Mastering Playwright with TS](https://www.udemy.com/course/mastering-playwright-test-automation-with-typescript/).

### Test pyramid (in this project)

| Layer | Tool | Target |
|---|---|---|
| Unit | Vitest | ~20: `daysUntil`, `addMonths`, money formatting, renewal logic |
| Integration | Supertest | ~15: every endpoint, incl. 401/403 paths |
| E2E | Playwright | ~8: critical user journeys only |

Playwright specifics: Page Object Model (`LoginPage`, `ItemsPage`, `DashboardPage`); `storageState` fixtures for auth; locator order `getByRole > getByLabel > getByTestId > CSS`, **never XPath**; `expect` auto-retry (no `waitForTimeout`); test isolation (each test seeds its own data); trace viewer + `--ui` mode.

**Interview note:** be able to *talk* Selenium (WebDriver architecture, waits, why Playwright's auto-waiting is better) even though you build in Playwright — service companies still ask.

## Career track (starts in the build phase, not at the end)

Resume leads with **banking domain + 2 YOE + automation**. LinkedIn: "QA Engineer | Automation (Playwright/TypeScript) | Banking Domain". Start applying mid-program. Anki deck of ~50 SDET questions. Mock interviews with Thomas: walk the repo, defend design decisions.
