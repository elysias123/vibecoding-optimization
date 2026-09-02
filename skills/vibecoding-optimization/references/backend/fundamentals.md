# Backend Fundamentals

Load this reference for cross-cutting backend work: API design, database patterns, authentication, or authorization. Apply it with the stack-specific reference.

## API design

<api-rules>
  <rule>Use plural resource nouns and HTTP verbs: /users, not /user.</rule>
  <rule>Return a consistent error shape: { "error": { "code": "...", "message": "..." } } with an appropriate HTTP status.</rule>
  <rule>Prefer cursor pagination for large datasets; allow offset pagination for small, stable datasets.</rule>
  <rule>Use /v1/ path versioning for public APIs and header versioning for internal services.</rule>
  <rule>Validate all input at the boundary; never trust client data.</rule>
  <rule>Apply rate and request-size limits to public endpoints.</rule>
</api-rules>

## Database patterns

<database-rules>
  <rule>Use an ORM or query builder for business logic; reserve raw SQL for performance-critical paths.</rule>
  <rule>Use migrations for every schema change; never alter production schemas manually.</rule>
  <rule>Index foreign keys and frequently queried columns without over-indexing write-heavy tables.</rule>
  <rule>Use transactions for multi-step writes that must be atomic.</rule>
  <rule>Use connection pooling in production.</rule>
</database-rules>

## Authentication and authorization

<auth-rules>
  <rule>Hash passwords with bcrypt, argon2, or scrypt; never store plaintext, MD5, or SHA hashes.</rule>
  <rule>Use JWT for stateless APIs and session cookies with CSRF protection for server-rendered applications.</rule>
  <rule>Validate permissions on the server for every protected operation.</rule>
  <rule>Use short-lived access tokens (15 to 30 minutes) and refresh tokens.</rule>
  <rule>Store secrets in environment variables or a secret manager, never source code.</rule>
</auth-rules>

## Observability

<observability-rules>
  <rule>Emit structured JSON logs with a request ID.</rule>
  <rule>Provide a /health or /healthz endpoint for load balancers.</rule>
  <rule>Track request latency, error rate, and database query duration.</rule>
</observability-rules>
