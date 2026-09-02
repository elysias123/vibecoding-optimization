# Go Backend Reference

Load for Go backend work using net/http, Gin, Echo, or Fiber.

<external-skills><status>No curated external skills are available. Use the built-in fallback.</status></external-skills>

## Built-in fallback

<fallback-rules>
  <rule category="Framework">Use net/http for zero dependencies, Gin or Echo for middleware ecosystems, and Fiber for an Express-like API.</rule>
  <rule category="Structure">Use cmd/ for entry points, internal/ for private packages, and pkg/ for public libraries.</rule>
  <rule category="Errors">Return error last, wrap with fmt.Errorf("context: %w", err), and never panic in library code.</rule>
  <rule category="Database">Use database/sql with pgx for PostgreSQL, GORM for convenience, or sqlc for type-safe SQL.</rule>
  <rule category="Auth">Use golang-jwt/jwt with middleware authentication; keep secrets in environment variables.</rule>
  <rule category="Concurrency">Use goroutines and channels; pass context.Context for cancellation and timeouts.</rule>
  <rule category="Validation">Use go-playground/validator tags or custom validation middleware.</rule>
  <rule category="Testing">Use testing, optionally testify for assertions, and httptest for handler tests.</rule>
  <rule category="Build">Use go build with ldflags for version injection and multi-stage Docker builds.</rule>
</fallback-rules>
