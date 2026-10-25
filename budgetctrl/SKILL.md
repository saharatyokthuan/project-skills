# budgetctrl Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with budgetctrl — multi-page static HTML/JS budget tracker with PWA support.

**When to Use:** Working on the budgetctrl project — adding pages, modifying data layer, PWA features.

## Overview

Multi-page finance app (not single-page like Cash-Flow/pos-mobile). Pages: `index.html`, `dashboard.html`, `transactions.html`, `budget.html`, `debts.html`, `goals.html`, `recurring.html`, `settings.html`.

Modular JavaScript in `js/`:

- `js/db.js` — data layer (localStorage wrapper)
- `js/nav.js` — navigation between pages
- `js/utils.js` — shared utilities
- Per-page modules: `dashboard.js`, `transactions.js`, `budget.js`, `debts.js`, `goals.js`, `recurring.js`, `settings.js`

PWA support: `manifest.json` + `sw.js` (service worker) for offline capability.

CSS: `css/style.css` for styling.

## Interface

### Inputs

- 8 HTML pages in root
- `js/db.js` — central data store
- `js/nav.js` — page routing
- Per-page JS modules
- `manifest.json`, `sw.js` — PWA config

### Outputs

- New/modified pages and JS modules
- Updated data schema in db.js

## Usage

```bash
# Run locally
cd /root/projects/budgetctrl
open index.html
# or
python3 -m http.server 8000
```

## Examples

### Example 1: Add new page

```bash
# 1. Create newpage.html with standard structure
# 2. Create js/newpage.js with page-specific logic
# 3. Add navigation in js/nav.js
# 4. Link JS in newpage.html
# 5. Update service worker cache list if needed
```

### Example 2: Extend data model

```bash
# 1. Modify js/db.js: add new store/key
# 2. Update load/save logic
# 3. Add migration in load() for existing users
# 4. Update relevant page modules
```

## Constraints & Rules

- Multi-page (not SPA) — each page loads separately
- Shared data via js/db.js — single source of truth
- Navigation via js/nav.js — consistent across pages
- PWA: manifest.json + sw.js must be updated for new assets
- localStorage schema changes require migration in db.js load()
- No build step — direct HTML/JS/CSS

## Related Skills

- Cash-Flow (similar domain, different architecture)
- systematic-debugging

## References

- `/root/projects/budgetctrl/js/db.js` — data layer
- `/root/projects/budgetctrl/js/nav.js` — navigation
- `/root/projects/budgetctrl/manifest.json` — PWA config
