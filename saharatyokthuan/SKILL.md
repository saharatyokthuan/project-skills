# saharatyokthuan Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with saharatyokthuan — GitHub profile README with dynamic badges, stats, and animations.

**When to Use:** Updating the GitHub profile README for user saharatyokthuan.

## Overview

Elaborate GitHub profile README with:
- Animated banner (capsule-render)
- Typing SVG animation (readme-typing-svg)
- Profile stats cards (github-readme-stats)
- Top languages card
- Streak stats
- Activity graph
- Snake animation (github-snake)
- Contact badges (email, LinkedIn, portfolio, LINE, Discord, Telegram, social media)
- Thai/English language toggle

All content in single `README.md` with external service URLs for dynamic images.

## Interface

### Inputs
- `README.md` — profile content with dynamic badge URLs
- `README-en.md` — English version

### Outputs
- Updated `README.md` / `README-en.md`

## Usage

```bash
# Edit directly
cd /root/projects/saharatyokthuan
# Modify README.md or README-en.md
git commit -am "docs: update profile"
git push
```

## Examples

### Example 1: Update banner
```bash
# Modify capsule-render.vercel.app URL parameters:
# - text=NAME, fontSize, fontAlignY
# - desc=TAGLINE, descSize, descAlignY
# - color=gradient, animation=fadeIn
```

### Example 2: Add new contact badge
```bash
# Add shields.io or custom-icon-badges.demolab.com badge
# Follow existing pattern: <a href="URL"><img src="BADGE_URL" alt="LABEL" /></a>
```

### Example 3: Update snake animation
```bash
# Requires .github/workflows/snake.yml to run
# Output commits to output/github-snake.svg
# Reference in README with picture element for dark/light mode
```

## Constraints & Rules

- All dynamic content via external services (vercel, demolab, vercel.app, etc.)
- Thai primary, English secondary (README-en.md)
- Snake animation requires GitHub Action workflow
- Stats cards hit rate limits — consider self-hosting github-readme-stats
- Profile views badge uses komarev.com/ghpvc
- Use picture element for dark/light mode images

## Related Skills

- j-bunrod (simpler profile README)

## References

- `/root/projects/saharatyokthuan/README.md` — Thai version
- `/root/projects/saharatyokthuan/README-en.md` — English version
