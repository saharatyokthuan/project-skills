# pos-mobile Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with the pos-mobile static Thai POS SPA (single-page, localStorage, optional Docker backend).

**When to Use:** Working on the pos-mobile project — adding POS features, fixing bugs, or understanding the codebase.

## Overview

pos-mobile is a single-page Thai Point of Sale application. All pages in `index.html` switched via `showPage()`. Three core files:

- `index.html` — header, sidebar, all pages, all modals
- `style-pos.css` — theme, layout, responsive, receipt print styles
- `script-pos.js` — all logic: data management, rendering, calculations, navigation

Optional `master-products.js` (not in repo) for central product list — app auto-hides related UI if missing.

CDN dependencies with SRI:

- SheetJS 0.18.5 (Excel import/export)
- Chart.js 4.4.0 (report charts)

Barcode scanning requires `https://` or `localhost`.

Data stored in browser localStorage only — no server sync by default. Export/import via JSON backup.

## Interface

### Inputs

- `index.html` — single-page structure with all views
- `style-pos.css` — theming and responsive styles
- `script-pos.js` — complete application logic

### Outputs

- Modified core files for new features/fixes
- Optional `master-products.js` for product database

## Usage

```bash
# Run locally (static)
open index.html
# or
python3 -m http.server 8000

# Full stack with Docker backend
docker-compose up
```

## Examples

### Example 1: Add a new report tab

```bash
# 1. Add tab button in index.html report section
# 2. Add tab content div with canvas/chart container
# 3. Add chart rendering logic in script-pos.js using Chart.js
# 4. Add export logic using SheetJS (XLSX)
```

### Example 2: Modify receipt printing

```bash
# Receipt styles in style-pos.css @media print section
# Print logic in script-pos.js printReceipt() function
```

## Constraints & Rules

- Single-page app — all views in index.html, switched via showPage()
- No ES modules — global functions, inline onclick handlers
- localStorage only — keys: products, sales, purchases, debts, expenses, settings, heldBills, categories
- Barcode scanning requires secure context (https:// or localhost)
- CDN deps with SRI — update hash if version changes
- Thai UI copy; code mixes Thai/English
- Optional master-products.js auto-detected — hide UI if missing

## Related Skills

- pos-mobile-labs (variant with multi-store backend)
- systematic-debugging

## References

- `/root/projects/pos-mobile/README.md` — user/developer guide
- `/root/projects/pos-mobile/docker-compose.yml` — backend stack
- `/root/projects/pos-mobile/script-pos.js` — source of truth