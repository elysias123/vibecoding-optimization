# Node.js Backend Reference

Load for Node.js backend work using Express, Fastify, Hono, or NestJS.

<external-skills><status>No curated external skills are available. Use the built-in fallback.</status></external-skills>

## Built-in fallback

<fallback-rules>
  <rule category="Framework">Use Express for ecosystem breadth, Fastify for performance, Hono for lightweight edge work, and NestJS for enterprise structure.</rule>
  <rule category="Structure">Prefer feature modules such as /modules/users/ over global controller/service layers.</rule>
  <rule category="Errors">Use centralized error middleware and protect against unhandled rejections.</rule>
  <rule category="Database">Use Prisma for type-safe migrations or Drizzle for SQL-close access; avoid raw queries in business logic.</rule>
  <rule category="Auth">Use JWT for stateless APIs or sessions for SSR; hash passwords with bcrypt or argon2; never store secrets in code.</rule>
  <rule category="Validation">Validate request bodies, params, and queries early with Zod.</rule>
  <rule category="Logging">Use structured JSON logs such as pino or winston and include a request ID.</rule>
  <rule category="Testing">Use Vitest or Jest for units and Supertest for HTTP integration tests.</rule>
  <rule category="TypeScript">Enable strict mode and define request and response shapes.</rule>
</fallback-rules>
