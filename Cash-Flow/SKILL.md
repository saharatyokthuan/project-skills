# Cash-Flow Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with the Cash-Flow static Thai personal finance SPA (HTML/JS/CSS, localStorage).

**When to Use:** Working on the Cash-Flow project — adding features, fixing bugs, or understanding the codebase.

## Overview

Cash-Flow is a single-page Thai finance application with no framework, build step, or package manager. All logic lives in `script.js` — data, rendering, charts, import/export, and event wiring. Data persists in a single localStorage key `cashflow_v1` containing items, wallets, categories, installments, and bills.

Key architectural patterns:

- Global `db` = persisted data; global `ui` = transient view state
- After mutating `db`, call `save()` then `renderAll()` or specific renderer
- No ES modules — inline HTML handlers call global `function` declarations
- New handlers added to `Object.assign(window, {...})` block at end of `script.js`
- Escape user-controlled values in `innerHTML` with `escapeHTML()`
- Money stored as plain JS numbers (THB); formatted only for display with `money()`
- Dates are local `YYYY-MM-DD` strings; use `todayStr()` / `addMonth()`; `fmtDate()` shows Buddhist-era year
- Transfers create two items with category exactly `โอนเงิน`; totals/charts exclude this category
- Loan page is derived: income category `ยืมเงิน`, expense category `คืนเงินกู้`, grouped by item name
- Excel import uses SheetJS (global `XLSX`) from CDN with SRI hash
- Charts are hand-drawn on Canvas (`drawBar`, `drawDonut`); HiDPI scaling in `prepCanvas`

## Interface

### Inputs

- `index.html` — all page sections, modals, inline `onclick` handlers
- `script.js` — entire app logic
- `style.css` — dark neon-gold theme with CSS variables

### Outputs

- Modified `script.js` with new features/fixes
- Updated `index.html` for new pages/modals
- Updated `style.css` for theme changes

## Usage

```bash
# Serve locally
cd /root/projects/Cash-Flow
python3 -m http.server 8000

# Syntax check only
node --check script.js
```

## Examples

### Example 1: Add a new page

```bash
# 1. Add <section class="page" id="page-new"> in index.html with sidebar button calling showPage('page-new', this)
# 2. Add renderer function in script.js and call from showPage() when page becomes active
# 3. Add any new handler to Object.assign(window, {...}) block in script.js
```

### Example 2: Add a new category

```bash
# Categories stored in db.cats array. Add to default cats in load() or via UI.
# Remember: escapeHTML() for any user-controlled values rendered via innerHTML
```

## Constraints & Rules

- No ES modules — use global functions and `Object.assign(window, {...})`
- Always call `save()` after mutating `db`, then `renderAll()` or specific renderer
- Escape all user-controlled values in `innerHTML` with `escapeHTML()`
- Money = plain numbers; format only for display with `money()`
- Dates = local `YYYY-MM-DD` strings; never use `new Date('YYYY-MM-DD')` or `toISOString()`
- Transfer category must be exactly `โอนเงิน`; totals/charts exclude it
- Loan categories `ยืมเงิน` / `คืนเงินกู้` are derived — renaming/deleting empties loan view
- SheetJS CDN version bump requires SRI hash update in `index.html`
- UI copy must be Thai; code identifiers/comments mix Thai and English
- Conventional Commits: `fix:`, `perf:`, `docs:` sometimes with Thai subjects

## Related Skills

- systematic-debugging (for debugging Cash-Flow issues)
- test-driven-development (no test suite exists — manual browser verification only)

## References

- `/root/projects/Cash-Flow/AGENTS.md` — canonical per-project guide
- `/root/projects/Cash-Flow/script.js` — source of truth
- `/root/projects/Cash-Flow/index.html` — all page sections and handlers
