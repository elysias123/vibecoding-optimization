# Java Backend Reference

> Loaded on demand when the task involves Java backend (Spring Boot, Quarkus, Micronaut).

## External Skills

> No curated agent skills available yet. As the ecosystem matures, external skill URLs will be added here.

## Fallback: Java Best Practices

- **Framework choice**: Spring Boot (ecosystem, enterprise standard), Quarkus (cloud-native, fast startup), Micronaut (compile-time DI, low memory).
- **Project structure**: layered packages per domain — `controller/`, `service/`, `repository/`, `dto/`, `entity/`. Use multi-module Maven/Gradle for large projects.
- **Dependency injection**: prefer constructor injection; avoid field injection with `@Autowired`.
- **Database**: Spring Data JPA + Hibernate for ORM; jOOQ for type-safe SQL. Use Flyway or Liquibase for migrations.
- **Validation**: Bean Validation (`@Valid`, `@NotNull`, `@Size`, etc.) on DTOs at controller layer.
- **Error handling**: `@ControllerAdvice` + `@ExceptionHandler` for global exception handling; return structured error responses.
- **Auth**: Spring Security for authentication/authorization. Use BCryptPasswordEncoder for password hashing. OAuth2/JWT via `spring-boot-starter-oauth2-resource-server`.
- **Async**: `@Async` for simple background tasks; Spring WebFlux or virtual threads (Java 21+) for reactive/high-concurrency workloads.
- **Testing**: JUnit 5 + Mockito for unit tests; `@SpringBootTest` + `MockMvc` for integration tests; Testcontainers for DB integration.
- **Build**: Maven or Gradle. Use Spring Boot plugin for fat JAR. Multi-stage Docker builds for production images.
- **Logging**: SLF4J + Logback (Spring Boot default). Use MDC for request-scoped context (request ID, user ID).
