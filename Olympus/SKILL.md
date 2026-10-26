# Olympus Skill

> **For agentic workers:** REQUIRED SUB-SKILL: N/A

**Purpose:** Skill for working with Olympus — multi-platform bot monorepo (Telegram + Discord).

**When to Use:** Working on Apollo (Telegram/Telegraf) or Artemis (Discord/discord.js) bots.

## Overview

Two independent bots in one repo:

- **Apollo** (`Apollo/telegram-bot/`) — Telegram bot using Telegraf ^4.15.3
- **Artemis** (`Artemis/`) — Discord bot using discord.js ^14.14.1

Both use `dotenv` ^16.3.1 for environment config. Each has its own `package.json`, `src/`, and `README.md`.

## Interface

### Inputs

- `Apollo/telegram-bot/src/` — Telegram bot source
- `Apollo/telegram-bot/package.json` — deps: telegraf, dotenv
- `Artemis/src/` — Discord bot source
- `Artemis/package.json` — deps: discord.js, dotenv
- `.env` files (not in repo) — `BOT_TOKEN`, `DISCORD_TOKEN`

### Outputs

- New bot commands, handlers, middleware
- Updated dependencies

## Usage

```bash
# Telegram Bot (Apollo)
cd /root/projects/Olympus/Apollo/telegram-bot
cp .env.example .env  # add BOT_TOKEN
npm install
npm start

# Discord Bot (Artemis)
cd /root/projects/Olympus/Artemis
cp .env.example .env  # add DISCORD_TOKEN
npm install
npm start
```

## Examples

### Example 1: Add Telegram command

```bash
# 1. Create handler in Apollo/telegram-bot/src/commands/
# 2. Register in main bot setup
# 3. Test with BotFather token
```

### Example 2: Add Discord slash command

```bash
# 1. Create command in Artemis/src/commands/
# 2. Register in deploy-commands.js or main index
# 3. Deploy with REST API
# 4. Test in Discord
```

## Constraints & Rules

- Each bot completely independent — separate node_modules, package.json, src
- Environment variables required: `BOT_TOKEN` (Telegram), `DISCORD_TOKEN` (Discord)
- Telegraf v4 patterns for Telegram; discord.js v14 patterns for Discord
- Both use dotenv for config — never commit .env files
- Default branch: main
- MIT License

## Related Skills

- pos-mobile-labs (Node.js backend patterns)

## References

- `/root/projects/Olympus/README.md` — setup guide
- `/root/projects/Olympus/Apollo/telegram-bot/README.md` — Telegram bot docs
- `/root/projects/Olympus/Artemis/README.md` — Discord bot docs