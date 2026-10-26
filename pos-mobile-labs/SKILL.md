# pos-mobile-labs Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working on pos-mobile-labs — POS-MOBILE variant with multi-store FastAPI backend, Alembic migrations, WebSocket sync.

**When to Use:** Working on the pos-mobile-labs project — backend API, database migrations, multi-store features, real-time sync.

## Overview

pos-mobile-labs extends pos-mobile with a full backend stack:

- **Frontend**: Same `index.html`, `style-pos.css`, `script-pos.js` as pos-mobile
- **Backend**: FastAPI + SQLite + Alembic migrations in `backend/`
  - `backend/app/main.py` — FastAPI entry point
  - `backend/app/models/` — SQLAlchemy models
  - `backend/app/api/` — REST endpoints (products, sales, purchases, debts, expenses, stores, sync, websocket)
  - `backend/app/services/` — business logic layer
  - `backend/alembic/versions/` — migration scripts (001_initial, 002_auth, 003_multi_store)
- **Sync**: WebSocket manager for real-time multi-device sync
- **Tests**: pytest in `backend/tests/` (14 test modules)

Docker Compose orchestration in `docker-compose.yml` with nginx reverse proxy.

## Interface

### Inputs

- `backend/app/` — FastAPI application
- `backend/alembic/` — database migrations
- `backend/tests/` — pytest test suite
- `docker-compose.yml` — full stack orchestration

### Outputs

- New API endpoints, services, models
- Alembic migration scripts
- WebSocket event handlers
- Test cases

## Usage

```bash
# Full stack
docker-compose up

# Backend only (from backend/)
pip install -r requirements.txt
alembic upgrade head
python run.py

# Run tests
cd backend && pytest

# Generate migration
alembic revision --autogenerate -m "description"
```

## Examples

### Example 1: Add new API endpoint

```bash
# 1. Add model in backend/app/models/
# 2. Create service in backend/app/services/
# 3. Add API router in backend/app/api/
# 4. Register router in backend/app/main.py
# 5. Generate Alembic migration
# 6. Add tests in backend/tests/
```

### Example 2: Add WebSocket event

```bash
# 1. Add event type in backend/app/websocket.py
# 2. Handle in backend/app/websocket_manager.py
# 3. Emit from service layer after data changes
# 4. Handle in frontend script-pos.js
```

## Constraints & Rules

- Backend uses FastAPI, SQLAlchemy, Pydantic v2
- Alembic for all schema changes — never modify DB directly
- WebSocket sync: emit events after successful DB commits
- Multi-store: all queries scoped by store_id
- Tests: pytest with conftest.py fixtures
- Docker: nginx proxies /api to backend, /ws to websocket
- Conventional Commits for git history

## Related Skills

- pos-mobile (frontend shared)
- systematic-debugging
- test-driven-development

## References

- `/root/projects/pos-mobile-labs/backend/app/main.py` — FastAPI entry
- `/root/projects/pos-mobile-labs/docker-compose.yml` — stack definition
- `/root/projects/pos-mobile-labs/backend/alembic/versions/` — migration history