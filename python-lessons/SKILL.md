# python-lessons Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with the Python data-analysis course — lessons, examples, exercises, and verification.

**When to Use:** Creating or modifying course content, fixing examples, updating exercises or test scripts.

## Overview

A 5-lesson Python course for beginners targeting data analysis/automation. Each lesson has:

- Markdown documentation in `lessons/lesson-XX.md` with problems + hidden solutions in `<details>`
- Multiple `.py` example files demonstrating concepts
- Lesson 5 capstone: `exercise1.py` with `exercise1_tests.json`
- Sample data: `sales.csv` (used from lesson 5)

Learning methodology: **Predict output before running** → type code manually → run → compare with solution.

Verification script at `~/.config/opencode/skills/code-teacher/scripts/check_exercise.py` runs exercise against test JSON.

## Interface

### Inputs

- `lessons/lesson-01.md` through `lesson-05.md` — lesson content
- `lesson1_basic.py`, `lesson2_*.py`, `lesson3_*.py`, `lesson4_*.py`, `lesson5_*.py` — examples
- `exercise1.py` — capstone project with `???` placeholders
- `exercise1_tests.json` — test cases for verification
- `sales.csv` — sample data

### Outputs

- Updated lesson docs, examples, exercises
- New test cases in `exercise*_tests.json`

## Usage

```bash
# Run examples
cd /root/projects/python-lessons
python3 lesson1_basic.py

# Verify exercise
python3 /root/.config/opencode/skills/code-teacher/scripts/check_exercise.py exercise1.py exercise1_tests.json
```

## Examples

### Example 1: Add new lesson

```bash
# 1. Create lessons/lesson-06.md with problems + <details> solutions
# 2. Create lesson6_*.py example files
# 3. Create exercise2.py with ??? placeholders
# 4. Create exercise2_tests.json with test cases
# 5. Update README.md course table
```

### Example 2: Fix broken example

```bash
# 1. Run the .py file to see error
# 2. Fix code — ensure it matches lesson concept
# 3. Verify it runs without error
# 4. Update lesson markdown if needed
```

## Constraints & Rules

- All example code must run without errors (tested)
- Lessons use `<details>` for hidden solutions in markdown
- Exercise files use `???` placeholders for students to fill
- Test JSON format: `{"tests": [{"input": {...}, "expected": {...}}, ...]}`
- Verification script expects specific JSON structure
- Learning rule: predict before running, type manually, read last error line first
- Thai language for docs/UI; code comments mix Thai/English

## Related Skills

- test-driven-development (for exercise verification)
- systematic-debugging (for fixing broken examples)

## References

- `/root/projects/python-lessons/README.md` — course overview
- `/root/projects/python-lessons/manual.md` — usage commands, progress tracking
- `/root/.config/opencode/skills/code-teacher/scripts/check_exercise.py` — verifier
