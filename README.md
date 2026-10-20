# claude-beta-tester

> A Claude Code plugin that runs AI-powered browser testing against any URL using personality-driven agents — speedrunners, chaos gremlins, skeptical executives, and more.

## Plugin Installation (Claude Plugin Directory)

Once listed in the Claude plugin directory:
```bash
claude plugin install claude-beta-tester@claude-community
```

Commands will be available as `/claude-beta-tester:beta-test`.

## Manual Install

```bash
# Clone into your Claude config directory
git clone https://github.com/rjspence3/claude-beta-tester ~/.claude/plugins/claude-beta-tester

# Copy command
cp ~/.claude/plugins/claude-beta-tester/.claude/commands/beta-test.md ~/.claude/commands/
```

Command is available immediately in Claude Code as `/beta-test`.

## What it does

`/beta-test` runs the `ai-beta-test` CLI against a target URL with one or more personality-driven agents. Each agent has a different mindset and surfaces different categories of issues.

### Available personalities

| Name | Mindset | What it surfaces |
|------|---------|-----------------|
| `speedrunner` | *"I don't have time for this."* | Missing loading states, unclear primary actions, broken fast-paths |
| `chaos_gremlin` | *"What happens if I do this?"* | Input validation gaps, error handling issues, state corruption |
| `skeptical_exec` | *"I don't trust this tool yet."* | Cognitive load, trust breaks, unexpected transitions |
| `methodical_newcomer` | *"I am new here."* | Missing guidance, confusing labels, dead ends |
| `overloaded_manager` | *"I have 30 seconds."* | Poor hierarchy, information overload, slow landing |
| `calm_operator` | *"Slow and steady."* | Missing feedback, inconsistency, unclear state |
| `adhd_founder` | *"Oh look, a shiny feature!"* | Poor resumption, brittle state, punitive flows |
| `privacy_paranoid` | *"Why do you need to know that?"* | Trust breaks, missing provenance, dark patterns |
| `feature_explorer` | *"Show me everything."* | Undiscoverable features, navigation gaps |
| `interactive_explorer` | *"I'll use every single one."* | Incomplete flows, missing feedback |
| `technical_exploit` | *"I don't play by the rules."* | Security hints, exposed storage, validation bypasses |
| `hybrid_auditor` | *"I read the blueprints."* | Security risks, logic errors, API failures |
| `agentic_interface_tester` | *"AI interface UX researcher."* | Mode selection errors, decision transparency |

**Default set:** `speedrunner`, `chaos_gremlin`, `skeptical_exec`

## Usage

```
/beta-test
```

Claude will ask for:
1. Target URL
2. Goal (one sentence — e.g., "Complete the onboarding flow")
3. Personalities to run (or say `default`)

Or provide them directly:

```
/beta-test https://myapp.com
```

## Requirements

Requires `ai-beta-test` CLI and Node.js 18+:

```bash
# From the repo (development)
pip install -e ~/Development/ai-beta-tester

# Or once published
pip install ai-beta-tester

# Node.js (required for Playwright MCP server)
brew install node
```

---

Built by [Rob Spence](https://nomouthlabs.com). MIT License.
