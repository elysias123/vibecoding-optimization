# Go Backend Reference

> Loaded on demand when the task involves Go backend (net/http, Gin, Echo, Fiber).

## External Skills

> No curated agent skills available yet. As the ecosystem matures, external skill URLs will be added here.

## Fallback: Go Best Practices

- **Framework choice**: net/http (stdlib, zero deps), Gin/Echo (middleware ecosystem), Fiber (Express-like API).
- **Project structure**: `cmd/` (entry points), `internal/` (private packages), `pkg/` (public libraries). Follow golang-standards/project-layout as a starting reference.
- **Error handling**: return `error` as last return value; wrap errors with `fmt.Errorf("context: %w", err)`. No panic in library code.
- **Database**: `database/sql` + pgx (PostgreSQL) or GORM (convenience). Use `sqlc` for type-safe queries from SQL.
- **Auth**: JWT via `golang-jwt/jwt`; middleware-based authentication. Store secrets in environment variables.
- **Concurrency**: goroutines + channels for parallelism; use `context.Context` for cancellation and timeouts.
- **Validation**: go-playground/validator struct tags or custom validation middleware.
- **Testing**: stdlib `testing` package; `testify` for assertions; `httptest` for handler tests.
- **Build**: `go build` with `-ldflags` for version injection; multi-stage Docker builds for minimal images.
