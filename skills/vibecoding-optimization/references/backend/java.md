# Java Backend Reference

Load for Java backend work using Spring Boot, Quarkus, or Micronaut.

<external-skills><status>No curated external skills are available. Use the built-in fallback.</status></external-skills>

## Built-in fallback

<fallback-rules>
  <rule category="Framework">Use Spring Boot for ecosystem maturity, Quarkus for cloud-native fast startup, and Micronaut for compile-time DI and lower memory use.</rule>
  <rule category="Structure">Organize controller/, service/, repository/, dto/, and entity/ by domain; use multi-module Maven or Gradle for large projects.</rule>
  <rule category="DI">Prefer constructor injection; avoid field injection with @Autowired.</rule>
  <rule category="Database">Use Spring Data JPA plus Hibernate or jOOQ; use Flyway or Liquibase migrations.</rule>
  <rule category="Validation">Apply Bean Validation such as @Valid and @NotNull to controller DTOs.</rule>
  <rule category="Errors">Use @ControllerAdvice and @ExceptionHandler for structured global error responses.</rule>
  <rule category="Auth">Use Spring Security, BCryptPasswordEncoder, and OAuth2/JWT resource-server support where applicable.</rule>
  <rule category="Async">Use @Async for simple background work; use WebFlux or Java 21 virtual threads for reactive or high-concurrency work.</rule>
  <rule category="Testing">Use JUnit 5 and Mockito for units, @SpringBootTest and MockMvc for integration, and Testcontainers for database integration.</rule>
  <rule category="Build">Use Maven or Gradle with the Spring Boot plugin and multi-stage Docker builds.</rule>
  <rule category="Logging">Use SLF4J and Logback with MDC request and user context.</rule>
</fallback-rules>
