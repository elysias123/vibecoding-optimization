# Rust Backend Reference

> Loaded on demand when the task involves Rust backend (Actix-web, Axum, Rocket).

## External Skills

> No curated agent skills available yet. As the ecosystem matures, external skill URLs will be added here.

## Fallback: Rust Best Practices

- **Framework choice**: Axum (tokio ecosystem, modular), Actix-web (mature, high throughput), Rocket (ergonomic, macro-heavy).
- **Project structure**: `src/main.rs` (entry), `src/routes/`, `src/handlers/`, `src/models/`, `src/db/`. Use Cargo workspaces for multi-crate projects.
- **Error handling**: define a custom `AppError` enum implementing `IntoResponse` (Axum) or `ResponseError` (Actix). Use `thiserror` for library errors, `anyhow` for application-level errors. Never use `unwrap()` in production code paths.
- **Database**: SQLx (async, compile-time checked queries) or Diesel (sync, strong type safety). Use SQLx migrations or `diesel_migrations`.
- **Auth**: JWT via `jsonwebtoken` crate; middleware/extractor-based authentication. Use `argon2` crate for password hashing.
- **Async**: tokio runtime is standard. Use `tokio::spawn` for background tasks, `tokio::select!` for concurrent operations. Avoid blocking the async runtime (`spawn_blocking` for CPU-heavy work).
- **Validation**: `validator` crate with derive macros on request structs; validate at handler entry.
- **Serialization**: serde + serde_json for request/response (de)serialization. Derive `Serialize`/`Deserialize` on all API types.
- **Testing**: `#[tokio::test]` for async tests; `tower::ServiceExt` for Axum handler testing; `actix_web::test` for Actix. Use `testcontainers-rs` for DB integration tests.
- **Build**: `cargo build --release` with LTO for optimized binaries. Multi-stage Docker builds (`rust:slim` builder + `debian:slim` runtime).
- **Safety**: prefer safe Rust; `unsafe` blocks require a `// SAFETY:` comment explaining the invariant.
