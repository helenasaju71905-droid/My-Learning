# Thomas — TypeScript + MCP/AI Track

Thomas learns TypeScript by **assisting on simple API/DB tasks**, then builds his signature work: an **MCP server + AI layer from scratch in TypeScript**.

## Phase 2 — Learn TS by assisting

Take simple, well-scoped API/DB tasks (a `GET` endpoint, a Zod schema, a small service function) to build real TypeScript-in-an-API muscle. These are normal `feat/*` PRs into `dev`, reviewed like any other.

Also in Phase 2: **scaffold the MCP server against stub/mock data** so the structure is ready before the real `/reports/*` endpoints land.

## Phase 3 — Specialty: MCP/AI layer

Docs: [MCP](https://modelcontextprotocol.io/) · [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) · [v2 SDK docs / 10-min server](https://ts.sdk.modelcontextprotocol.io/v2/) · MCP Inspector for live tool testing.
Aggregated guide (free): [Scrimba — Best MCP Courses 2026](https://scrimba.com/articles/best-mcp-tutorials-and-courses/).
Udemy (pick one): [MCP Crash Course](https://www.udemy.com/course/model-context-protocol/) · [MCP Bootcamp](https://www.udemy.com/course/learn-mcp-model-context-protocol-course-and-a2a-bootcamphands-hands-on/) · [topic page](https://www.udemy.com/topic/model-context-protocol-mcp/).

### Design

- **Read-only** MCP server exposing the app's `/reports/*` endpoints as a **fixed toolset** — *not* text-to-SQL. Item names are attacker-controlled text flowing into a prompt; unbounded SQL is a security and cost problem.
- Reuse the `/shared` Zod schemas as **tool input schemas** — the same schemas Helena wrote in Phase 1 become MCP tool contracts. One source of truth.
- Tools map ~1:1 to the report endpoints: expiring items, spend by category, lapsed renewals.

### Why the API is designed this way

The `/reports/*` endpoints are deliberately **narrow parameterized queries**, not one generic filter endpoint — precisely so they translate cleanly into safe, bounded MCP tools.

## Deliverable / gate

MCP server runs; its tools are callable end-to-end (verified in MCP Inspector) against the real API, returning validated, schema-typed results.
