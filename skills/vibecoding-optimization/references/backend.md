# Backend Task Router

> **This file is the entry point for backend tasks.** It contains ONLY a routing table and loading rules.
> Detailed skill references and fallback best practices are in sub-files under `references/backend/`.
> **Do NOT load sub-files unless the routing table below directs you to.**

## Rules

1. Match the user's task to a row in the **Routing Table** below.
2. Load **only** the sub-file(s) indicated by the matched row. Do NOT preload other sub-files.
3. If an external skill (referenced inside a sub-file) is not installed and cannot be fetched from its URL, skip it and continue.
4. If no external skills can be obtained at all, each sub-file contains its own fallback section — use that and note it in output.
5. For cross-cutting concerns (API design, database, auth), load `references/backend/fundamentals.md` alongside the stack-specific file.

## Routing Table

| Task signal | Load file |
|-------------|-----------|
| Node.js / Express / Fastify / NestJS / Hono | `references/backend/nodejs.md` |
| Python / FastAPI / Flask / Django | `references/backend/python.md` |
| Go / Gin / Echo / Fiber | `references/backend/go.md` |
| Java / Spring Boot / Quarkus / Micronaut | `references/backend/java.md` |
| Rust / Actix-web / Axum / Rocket | `references/backend/rust.md` |
| API design (REST / GraphQL) — any stack | `references/backend/fundamentals.md` |
| Database design / ORM — any stack | `references/backend/fundamentals.md` + stack-specific file |
| Authentication / Authorization — any stack | `references/backend/fundamentals.md` + stack-specific file |
| Other backend stacks (Ruby, PHP, C#, Elixir, etc.) | `references/backend/fundamentals.md` (apply general principles; no stack-specific file available) |

> As the backend skill ecosystem matures, this table will link to external SKILL.md files just like `frontend.md` does.

## Stack-Direction Alignment

When the main SKILL.md suggests a tech-stack direction, apply it **after** loading the relevant sub-file:
- **Simple & Fast**: use the simplest framework option from the sub-file; skip advanced patterns.
- **Maintainable**: use structured framework + ORM + validation layer.
- **High Performance**: use performance-oriented framework + optimized DB access + caching layer.
