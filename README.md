# Agentry Agent Skill

Agentry is agent-native analytics and logging for coding agents. It covers
product analytics, error logging, and deploy attribution through one HTTP API so
agents can answer what users did, what broke, and what changed.

## What Agentry Covers

- Product analytics for user, funnel, activation, retention, and business
  events.
- Error logging for exceptions, failed jobs, operational failures, and case
  context.
- Deploy attribution that connects production behavior to releases and code
  changes.
- Day-to-day agent reads for cases, analytics, deploys, query blueprints, event
  names, and saved signal maps.

## What This Skill Does

This repository contains the standalone Agentry skill for AI coding agents.

Use the skill when a user asks an agent to install, set up, or use Agentry; add
analytics, logging, error monitoring, deploy attribution, product telemetry, or
production debugging; investigate a production error or case; or answer
product/reliability questions from Agentry data.

The skill is intentionally compact. It is not an SDK, API proxy, or duplicate
install guide. It points agents to the canonical Agentry docs:

- Install: https://agentry.sh/install.md
- Daily use: https://agentry.sh/agentry.md
- API discovery: https://api.agentry.sh/
- OpenAPI: https://api.agentry.sh/v1/openapi.json
- Adapter install/update: https://api.agentry.sh/adapters

## Files

- `SKILL.md` - agent instructions and live doc pointers.
- `LICENSE` - MIT license.

## Direct Skill Install

```bash
mkdir -p ~/.codex/skills/agentry
curl -fsSL -A 'AgentryAgent/1.0' \
  https://agentry.sh/skill/agentry/SKILL.md \
  > ~/.codex/skills/agentry/SKILL.md
```

Agents should still follow the canonical install flow at
https://agentry.sh/install.md before modifying a project.
