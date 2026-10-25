# shiftmate Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with ShiftMate — shift-scheduling SPA with optional Flask+SQLite backend.

**When to Use:** Working on the shiftmate project — scheduling logic, UI, optional backend API, backup tools.

## Overview

ShiftMate is a mobile-first weekly shift scheduler (Mon–Sun). Core frontend: `index.html`, `style.css`, `app.js`. Optional backend in `backend/` (Flask + SQLite). Tools in `tools/` for backup/convert.

Key features:
- Day/Week/Month views, two table modes (row=employee or row=shift)
- Employee CRUD (code, name, position, phone)
- Shift CRUD (code, name, start/end time, color, cross-day, OT, OFF)
- Assign shifts via cell tap → modal with shift select + OT checkbox + copy from yesterday
- Summary: count per shift per day
- History view by Day/Week/Month
- Export/Import: JSON (full), CSV (row per emp×day×shift), XLSX (3 sheets)
- Reset clears all localStorage

Seed data: 8 shifts (M, A, N, T08, T10, T13, MGR, OFF) — editable in UI.

Business rules:
- 1 employee = 1 shift/day (no time overlap check — shifts naturally overlap)
- OT flag per shift → shows as `M +OT` chip
- OT checkbox only for shifts with `otUntil` set
- OFF is a normal assignable shift (gray chip)
- Cross-day shifts supported
- Summary excludes OFF from "working" count

Backend (optional): Flask REST API at `backend/app.py`, SQLite at `backend/database.py`. Frontend does NOT call this API — it's separate for server-side storage needs.

Tools: `tools/backup.py` (export/import via API), `tools/convert.py` (JSON ↔ CSV).

CSS theming via variables at top of `style.css` (`--c-primary`, `--c-bg`, etc.).

## Interface

### Inputs
- `index.html`, `style.css`, `app.js` — frontend SPA
- `backend/app.py`, `backend/database.py` — Flask API
- `tools/backup.py`, `tools/convert.py` — CLI tools

### Outputs
- Modified frontend/backend code
- New shift/employee business logic

## Usage

```bash
# Frontend only
python server.py          # serves on :8000, opens browser
# or
python -m http.server 8080

# Backend API (optional)
cd backend
pip install -r requirements.txt
python app.py             # :5000

# Tools
cd tools
python backup.py export
python backup.py import backup.json
python convert.py backup.json backup.csv
```

## Examples

### Example 1: Add new shift type
```bash
# 1. Add to seed data in app.js (shifts array) and backend/database.py
# 2. Add OT support if needed (otUntil field)
# 3. Update summary logic to handle new shift
# 4. Add color to CSS variables if new category
```

### Example 2: Add copy-week feature
```bash
# 1. Add button in UI (schedule page)
# 2. Implement in app.js: read current week, write to next week
# 3. Handle conflicts (existing assignments)
# 4. Update backend API if needed
```

## Constraints & Rules

- `python server.py` serves STATIC files only — NOT the Flask backend
- Frontend uses localStorage exclusively — backend API is separate
- Shift assignment: 1 emp = 1 shift/day enforced in UI
- OT only shown for shifts with otUntil configured
- OFF shift counted in assignments but excluded from summary "working"
- Export formats: JSON (full), CSV (flat), XLSX (3 sheets)
- Import REPLACES all data — warn user
- CSS variables at top of style.css for theming
- Responsive breakpoints: <768px mobile, ≥768px tablet, ≥1100px desktop

## Related Skills

- python-lessons (Python backend patterns)
- systematic-debugging

## References

- `/root/projects/shiftmate/README.md` — comprehensive guide
- `/root/projects/shiftmate/app.js` — frontend logic
- `/root/projects/shiftmate/backend/app.py` — Flask API
