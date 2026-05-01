# Backend Task Router

> Entry point for backend programming tasks. It contains only routing and loading rules.
> Load sub-files only when the main skill is active for the current turn and the routing table below matches.

## Rules

1. Use this router only after the main skill is activated for the current turn.
2. Match the task to the routing table and load only the listed sub-file(s); do not preload others.
3. If an external skill is unavailable, skip it and continue; if none are available, use the matched sub-file's fallback and note it in output.
4. For API design, database, or auth concerns, load `references/backend/fundamentals.md` alongside the stack-specific file. `references/backend/fundamentals.md` defines baseline cross-cutting constraints; stack-specific files refine implementation details within those constraints.

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

## Stack-Direction Alignment

When the main SKILL.md suggests a tech-stack direction, apply it **after** loading the relevant sub-file:
- **Simple & Fast**: use the simplest framework option from the sub-file; skip advanced patterns.
- **Maintainable**: use structured framework + ORM + validation layer.
- **High Performance**: use performance-oriented framework + optimized DB access + caching layer.
