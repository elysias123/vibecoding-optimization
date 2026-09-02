# Python Backend Reference

Load for Python backend work using FastAPI, Flask, or Django.

<external-skills><status>No curated external skills are available. Use the built-in fallback.</status></external-skills>

## Built-in fallback

<fallback-rules>
  <rule category="Framework">Use FastAPI for async and auto-docs, Flask for simplicity, and Django for batteries-included development.</rule>
  <rule category="Structure">Use domain-driven packages with routers/, services/, models/, and schemas/ per domain.</rule>
  <rule category="Types">Use type hints and Pydantic request and response models.</rule>
  <rule category="Database">Use SQLAlchemy 2.0 or Tortoise ORM and Alembic migrations.</rule>
  <rule category="Auth">Use OAuth2 and JWT through FastAPI security utilities, Django built-in auth where appropriate, and passlib hashing.</rule>
  <rule category="Async">Prefer async def endpoints for FastAPI I/O; avoid blocking calls in async contexts.</rule>
  <rule category="Errors">Use custom exception handlers and structured error responses.</rule>
  <rule category="Testing">Use pytest with httpx.AsyncClient for FastAPI or the Django test client.</rule>
  <rule category="Dependencies">Use pyproject.toml with uv or poetry and pin production dependencies.</rule>
</fallback-rules>
