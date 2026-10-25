# vender Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with vender — offline-first vending stock manager (single file, no dependencies).

**When to Use:** Working on the vender project — stock CRUD, categories, alerts, JSON backup/restore.

## Overview

Single-file vending stock manager (originally `index.txt`, must rename to `index.html`). Offline-first, no dependencies, mobile-first (max-width 520px).

Features:
- Product CRUD with quick +/- stock buttons
- Categories with stock level bars
- Auto alerts: out of stock, below threshold, near expiry, expired
- Summary: SKU count, total items, total value, by category
- JSON export/import for backup/restore
- Responsive design for mobile

No build, no server, no dependencies — pure HTML/JS/CSS in one file.

## Interface

### Inputs
- `index.html` (renamed from `index.txt`) — entire application

### Outputs
- Modified `index.html` with new features/fixes

## Usage

```bash
# Setup
cd /root/projects/vender
mv index.txt index.html

# Run
open index.html
# or
python3 -m http.server 8000
```

## Examples

### Example 1: Add expiry tracking field
```bash
# 1. Add expiry date input to product form
# 2. Extend product object schema
# 3. Add alert logic for near/expired
# 4. Update summary calculations
# 5. Ensure JSON export/import includes new field
```

### Example 2: Add barcode scanning
```bash
# 1. Add camera access button (requires https:// or localhost)
# 2. Integrate barcode detection API
# 3. Auto-fill product code/name on scan
# 4. Handle offline gracefully
```

## Constraints & Rules

- Single file — all HTML/CSS/JS in index.html
- No external dependencies — vanilla JS only
- Mobile-first: max-width 520px, touch-friendly
- Offline-first: works without network after first load
- Data in localStorage — JSON backup/restore for portability
- Rename index.txt → index.html before use
- Thai UI language

## Related Skills

- budgetctrl (similar domain)
- Cash-Flow (finance patterns)

## References

- `/root/projects/vender/index.txt` — source (rename to .html)
- `/root/projects/vender/README.md` — user guide
