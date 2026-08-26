# TypeScript Roadmap (both learners)

Structured — TypeScript is the core skill and doesn't fully emerge from just building. One resource per stage, finished before moving on.

## Resources

| Stage | Topics | Resource |
|---|---|---|
| A. Fundamentals | types, functions, objects, unions, narrowing | [Total TypeScript — Beginner's Tutorial](https://www.totaltypescript.com/tutorials/beginners-typescript) (free) |
| B. Handbook depth | interfaces vs types, generics, `strict`, modules | [Official TS Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) |
| C. Applied | Zod, `Result<T,E>`, async, discriminated unions | [Total TypeScript free tutorials](https://www.totaltypescript.com/tutorials) |
| Checklist | overall skill map | [roadmap.sh/typescript](https://roadmap.sh/typescript) |

Setup: `pnpm add -D typescript tsx @types/node`, `tsconfig.json` with `"strict": true`. Run with `pnpm tsx file.ts`.

## Daily push schedule

One committed deliverable per working day on your `*/foundations` branch. Commit daily even if small — cadence is scored. ~15 working days (~3 weeks), alongside the Linux track in Phase 1. Files in `/practice`.

| Day | Push (file) | Teaches |
|---|---|---|
| 1 | setup + `01-greet.ts` | `tsconfig` `strict:true` + `tsx`; typed params/returns, template literals, `const`/`let` |
| 2 | `02-fizzbuzz.ts` | loops, conditionals, `%` |
| 3 | `03-dates.ts` | `daysUntil(date)`, `addMonths()` — real project code |
| 4 | `04-arrays.ts` | `map`/`filter`/`reduce`/`find`/`sort` over objects |
| 5 | `05-objects.ts` | `interface` vs `type`, optional `?`, `readonly`, nesting |
| 6 | `06-unions.ts` | literal unions, `RenewalType`, narrowing with `if` |
| 7 | `07-discriminated.ts` | discriminated unions + `switch` with `never` exhaustiveness |
| 8 | `08-money.ts` | integer minor units, `formatMoney()`, `parseMoney()` |
| 9 | `09-generics.ts` | `Result<T,E>`, `paginate<T>(items, page, size)` |
| 10 | `10-async.ts` | promises, `async/await`, `Promise.all`, try/catch, real `fetch` |
| 11 | `11-zod.ts` | parsing untrusted JSON, `z.infer<>` |
| 12 | `12-modules.ts` | `import`/`export`, folder structure, barrel files |
| 13 | `/shared/schemas.ts` (part 1) | Zod schemas: `User`, `Item` |
| 14 | `/shared/schemas.ts` (part 2) | Zod schemas: `Renewal`, `Household` + `z.infer` types |
| 15 | strict-pass refactor | remove every `any`, enable stricter flags, self-review before the gate |

## Banned (a review comment if reached for)

`any`, `enum` (use literal unions), `as` casting, decorators, namespaces.

## Deliverable / gate

12 practice programs green, `/shared/schemas.ts` written, `strict: true`, zero `any`. The `/shared` Zod schemas later become request validation, DB shape, frontend types, and Thomas's MCP tool schemas — one source of truth.
