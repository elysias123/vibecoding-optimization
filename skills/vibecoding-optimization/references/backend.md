# Backend Task Router

Use this router only after the main skill is active. Load the smallest matching set of backend references.

<load-policy>
  <rule>Match the task, then load only the listed sub-file or files; never preload unrelated references.</rule>
  <rule>When an external skill is unavailable, use the matched file's fallback and state that in the result.</rule>
  <rule>For API design, database design, authentication, or authorization, load fundamentals.md with the stack-specific reference.</rule>
</load-policy>

## Routes

<routes>
  <route when="Node.js, Express, Fastify, NestJS, or Hono" load="references/backend/nodejs.md" />
  <route when="Python, FastAPI, Flask, or Django" load="references/backend/python.md" />
  <route when="Go, Gin, Echo, or Fiber" load="references/backend/go.md" />
  <route when="Java, Spring Boot, Quarkus, or Micronaut" load="references/backend/java.md" />
  <route when="Rust, Actix-web, Axum, or Rocket" load="references/backend/rust.md" />
  <route when="REST or GraphQL API design" load="references/backend/fundamentals.md" />
  <route when="database design or ORM" load="references/backend/fundamentals.md plus the stack-specific file" />
  <route when="authentication or authorization" load="references/backend/fundamentals.md plus the stack-specific file" />
  <route when="an unsupported backend stack" load="references/backend/fundamentals.md" note="Apply general principles." />
</routes>

## Stack direction

<stack-alignment>
  <simple-fast>Use the simplest framework option and skip advanced patterns.</simple-fast>
  <maintainable>Use a structured framework, ORM, and validation layer.</maintainable>
  <high-performance>Use a performance-oriented framework, optimized database access, and caching.</high-performance>
</stack-alignment>
