# Project Skills Repository

This repository contains skill definitions (SKILL.md) for each project in the workspace, organized by project folder.

## Projects

| Project | Description | Skill File |
| ------- | ----------- | ---------- |
| [Cash-Flow](./Cash-Flow/SKILL.md) | Static Thai finance SPA (HTML/JS/CSS, localStorage) | `Cash-Flow/SKILL.md` |
| [Olympus](./Olympus/SKILL.md) | Empty project | `Olympus/SKILL.md` |
| [budgetctrl](./budgetctrl/SKILL.md) | Static HTML/JS budget tracker | `budgetctrl/SKILL.md` |
| [finance-app](./finance-app/SKILL.md) | Finance application | `finance-app/SKILL.md` |
| [j-bunrod](./j-bunrod/SKILL.md) | GitHub profile README | `j-bunrod/SKILL.md` |
| [pos-mobile](./pos-mobile/SKILL.md) | Static Thai POS SPA | `pos-mobile/SKILL.md` |
| [pos-mobile-labs](./pos-mobile-labs/SKILL.md) | POS mobile experiments | `pos-mobile-labs/SKILL.md` |
| [python-lessons](./python-lessons/SKILL.md) | Python data-analysis course | `python-lessons/SKILL.md` |
| [saharatyokthuan](./saharatyokthuan/SKILL.md) | GitHub profile README | `saharatyokthuan/SKILL.md` |
| [shiftmate](./shiftmate/SKILL.md) | Shift-scheduling SPA with optional Flask backend | `shiftmate/SKILL.md` |
| [vender](./vender/SKILL.md) | Vendor management | `vender/SKILL.md` |

## Personal Assistant: Laura (ลอร่า)

This folder is set up so Claude Code acts as **Laura**, a Thai-speaking personal assistant and orchestrator. Laura delegates work to team members defined as subagents:

| Member | Definition | Role | Output (Notion) |
| ------ | ---------- | ---- | ------ |
| Laura | [CLAUDE.md](./CLAUDE.md) | Orchestrator — receives requests and delegates | — |
| idea | [.claude/agents/idea.md](./.claude/agents/idea.md) | Turns raw thoughts into structured idea cards | [💡 Idea Cards](https://app.notion.com/p/4c675d0a99f2449ca2777462429e4a45) |
| research | [.claude/agents/research.md](./.claude/agents/research.md) | Researches idea cards or direct topics with cited sources | [🔍 Research Reports](https://app.notion.com/p/12c0bd12fddb4ec59cc377ece6962492) |

## Structure

```text
project-skills/
├── Cash-Flow/
│   └── SKILL.md
├── Olympus/
│   └── SKILL.md
├── budgetctrl/
│   └── SKILL.md
├── finance-app/
│   └── SKILL.md
├── j-bunrod/
│   └── SKILL.md
├── pos-mobile/
│   └── SKILL.md
├── pos-mobile-labs/
│   └── SKILL.md
├── python-lessons/
│   └── SKILL.md
├── saharatyokthuan/
│   └── SKILL.md
├── shiftmate/
│   └── SKILL.md
├── vender/
│   └── SKILL.md
├── templates/
│   └── SKILL.md.template
├── .github/
│   └── workflows/
│       └── validate.yml
└── README.md
```

## Usage

Each project folder contains a `SKILL.md` file that defines skills specific to that project. Use the template at `templates/SKILL.md.template` to create new skills.

## Contributing

1. Fork the repository
2. Create a new skill file in the appropriate project folder (or create a new project folder)
3. Follow the template structure
4. Submit a pull request

## License

TBD
