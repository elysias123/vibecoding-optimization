# Node.js Backend Reference

> Loaded on demand when the task involves Node.js backend (Express, Fastify, Hono, NestJS).

## External Skills

> No curated agent skills available yet. As the ecosystem matures, external skill URLs will be added here.

## Fallback: Node.js Best Practices

- **Framework choice**: Express (ecosystem), Fastify (performance), Hono (edge/lightweight), NestJS (enterprise structure).
- **Project structure**: feature-based modules (`/modules/users/`, `/modules/orders/`) over layer-based (`/controllers/`, `/services/`).
- **Error handling**: centralized error middleware; never let unhandled rejections crash the process. Use `process.on('unhandledRejection')` as a safety net.
- **Database**: Prisma (type-safe, migrations) or Drizzle (lightweight, SQL-close). Avoid raw queries in business logic.
- **Auth**: JWT for stateless APIs; session + cookie for SSR. Use bcrypt/argon2 for password hashing. Never store secrets in code.
- **Validation**: Zod for request body/params/query. Validate early, fail fast.
- **Logging**: structured JSON logs (pino for Fastify, winston for Express). Include request ID for tracing.
- **Testing**: Vitest or Jest for unit tests; Supertest for HTTP integration tests.
- **TypeScript**: use strict mode; define types for request/response shapes.
