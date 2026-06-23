# Agentry Agent Skill

<p>
  <a href="https://agentry.sh">
    <img src="https://agentry.sh/brand/agentry-lockup-light.svg" alt="Agentry" width="248">
  </a>
</p>

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

## Supported Agent Surfaces

Agentry is distributed as a skill, MCP handoff, OpenAPI Action schema, and
repo-local instruction adapters for:

- Codex and Claude Code.
- Cursor, VS Code with GitHub Copilot, Visual Studio with GitHub Copilot, and
  GitHub Copilot coding agent.
- Devin Desktop/Windsurf Cascade, Cline, Roo Code, Continue, Zed, Gemini CLI,
  Aider, and OpenCode.
- ChatGPT custom GPT Actions, generic MCP clients, and AGENTS.md-aware agents.
- AGENTS.md-compatible agents such as Jules, Factory, Amp, goose, Warp,
  JetBrains Junie, Augment Code, Kilo Code, Phoenix, Semgrep, Ona, and UiPath
  coded agents.

The adapter manifest is the canonical place to discover the current native
file path for each client: https://api.agentry.sh/adapters.

## Related Public Surfaces

- Website: https://agentry.sh/
- Live skill: https://agentry.sh/skill/agentry/SKILL.md
- Skill repository: https://github.com/fr33dr4g0n/agentry-skill
- MCP package on npm: https://www.npmjs.com/package/@agentrysh/mcp
- MCP repository: https://github.com/fr33dr4g0n/agentry-public
- Codex marketplace catalog: https://github.com/fr33dr4g0n/agentry-public/blob/main/.agents/plugins/marketplace.json
- Claude marketplace catalog: https://github.com/fr33dr4g0n/agentry-public/blob/main/.claude-plugin/marketplace.json
- MCP registry name: `io.github.fr33dr4g0n/agentry-observability`

## Files

- `SKILL.md` - agent instructions and live doc pointers.
- `LICENSE` - MIT license.

## Direct Skill Install

For the Codex plugin UI, Agentry is distributed as a Git-backed marketplace
source. It will not appear in global Codex plugin search for unrelated accounts
until they add the marketplace source, receive a workspace share, or OpenAI
curates it:

```bash
codex plugin marketplace add fr33dr4g0n/agentry-public
codex plugin add agentry@agentry
```

The direct skill install works without the plugin UI:

```bash
mkdir -p ~/.codex/skills/agentry
curl -fsSL -A 'AgentryAgent/1.0' \
  https://agentry.sh/skill/agentry/SKILL.md \
  > ~/.codex/skills/agentry/SKILL.md
```

Agents should still follow the canonical install flow at
https://agentry.sh/install.md before modifying a project.
