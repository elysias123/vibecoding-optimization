# Rust Backend Reference

Load for Rust backend work using Actix-web, Axum, or Rocket.

<external-skills><status>No curated external skills are available. Use the built-in fallback.</status></external-skills>

## Built-in fallback

<fallback-rules>
  <rule category="Framework">Use Axum for the Tokio ecosystem, Actix-web for mature high throughput, and Rocket for ergonomic macro-heavy development.</rule>
  <rule category="Structure">Use src/main.rs, routes/, handlers/, models/, and db/; use Cargo workspaces for multiple crates.</rule>
  <rule category="Errors">Implement an AppError that converts to a response; use thiserror for library errors and anyhow for application errors; never unwrap in production paths.</rule>
  <rule category="Database">Use SQLx for async compile-time checked queries or Diesel for synchronous strong typing; use their migration tools.</rule>
  <rule category="Auth">Use jsonwebtoken with middleware or extractors and argon2 for password hashing.</rule>
  <rule category="Async">Use Tokio, tokio::spawn for background tasks, tokio::select! for concurrency, and spawn_blocking for CPU-heavy work.</rule>
  <rule category="Validation">Validate request structs at handler entry with validator derive macros.</rule>
  <rule category="Serialization">Use serde and serde_json; derive Serialize and Deserialize for API types.</rule>
  <rule category="Testing">Use #[tokio::test], tower::ServiceExt for Axum, actix_web::test for Actix, and testcontainers-rs for database integration.</rule>
  <rule category="Build">Use cargo build --release with LTO and multi-stage Docker builds.</rule>
  <rule category="Safety">Prefer safe Rust; every unsafe block requires a SAFETY comment stating its invariant.</rule>
</fallback-rules>
