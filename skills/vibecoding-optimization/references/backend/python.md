# Python Backend Reference

> Loaded on demand when the task involves Python backend (FastAPI, Flask, Django).

## External Skills

> No curated agent skills available yet. As the ecosystem matures, external skill URLs will be added here.

## Fallback: Python Best Practices

- **Framework choice**: FastAPI (async, auto-docs), Flask (simplicity), Django (batteries-included).
- **Project structure**: domain-driven packages; separate `routers/`, `services/`, `models/`, `schemas/` per domain.
- **Type safety**: type hints everywhere; Pydantic models for request/response validation.
- **Database**: SQLAlchemy 2.0 (async support) or Tortoise ORM. Use Alembic for migrations.
- **Auth**: OAuth2 + JWT via FastAPI's security utilities; Django has built-in auth. Use passlib for hashing.
- **Async**: prefer `async def` endpoints in FastAPI; use `asyncio` for concurrent I/O. Avoid blocking calls in async context.
- **Error handling**: custom exception handlers; return structured error responses.
- **Testing**: pytest with httpx.AsyncClient (FastAPI) or Django test client.
- **Dependency management**: use `pyproject.toml` + `uv` or `poetry`. Pin all production dependencies.
