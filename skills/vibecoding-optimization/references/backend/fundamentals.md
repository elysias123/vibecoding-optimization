# Backend Fundamentals

> Loaded on demand for cross-cutting backend concerns (API design, database patterns, auth).
> Stack-agnostic — apply alongside any stack-specific sub-file.

## API Design
- RESTful conventions: nouns for resources, HTTP verbs for actions, plural endpoints (`/users`, not `/user`).
- Consistent error response shape: `{ "error": { "code": "...", "message": "..." } }` with appropriate HTTP status codes.
- Pagination: cursor-based preferred for large datasets; offset-based acceptable for small, stable datasets.
- Versioning: URL path (`/v1/`) for public APIs; header-based for internal services.
- Input validation at the boundary; never trust client data.
- Rate limiting and request-size limits on all public endpoints.

## Database Patterns
- Use an ORM or query builder for business logic; reserve raw SQL for performance-critical paths.
- Always use migrations for schema changes; never modify production schemas manually.
- Index foreign keys and frequently queried columns. Avoid over-indexing write-heavy tables.
- Use transactions for multi-step writes that must be atomic.
- Connection pooling is mandatory for production deployments.

## Authentication & Authorization
- Hash passwords with bcrypt, argon2, or scrypt. Never store plaintext or MD5/SHA hashes.
- JWT for stateless APIs; session + cookie (with CSRF protection) for server-rendered apps.
- Validate permissions server-side for every protected operation.
- Token expiry: short-lived access tokens (15–60 min) + refresh tokens.
- Store secrets in environment variables or a secret manager; never in source code.

## Observability
- Structured JSON logs with request ID for tracing.
- Health-check endpoint (`/health` or `/healthz`) for load balancers.
- Track key metrics: request latency, error rate, DB query duration.
