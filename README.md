# Humanity-AI plugin

Work on the [Humanities-AI Rights Constitution](https://github.com/Humanity-AIquest/hrc)
from the agent you already use.

The plugin is deliberately thin. It holds a connection, four commands, and two
subagents. Everything that could ever need correcting — clause text, the
deliberation protocol, conduct rules — is served live by the MCP server, so a
fix reaches every member in seconds instead of waiting for them to update.

## Install

```
/plugin marketplace add Humanity-AIquest/plugin
/plugin install humanity-ai@humanity-ai
```

Then sign in when prompted. You need to be a verified member — see
[membership](https://github.com/Humanity-AIquest/hrc/blob/main/GOVERNANCE.md#membership).

## Not using Claude Code?

The MCP server works on its own with any client that speaks the protocol —
Claude Desktop, Cursor, Windsurf, VS Code, Zed. Add:

```json
{
  "mcpServers": {
    "humanity-ai": {
      "type": "http",
      "url": "https://mcp.humanity-ai.quest/v1"
    }
  }
}
```

You lose the slash commands and subagents; every tool still works.

## What's in it

| | |
|---|---|
| `/hrc <clause>` | Look up a clause with rationale and standing |
| `/where-do-i-stand` | What changed while you were away, what needs you |
| `/draft-amendment` | Draft, constitutionally check, and file an amendment |
| `/my-positions` | Your contribution record and where each entry landed |
| `clause-analyst` | Deep analysis of a clause before you form a position |
| `devils-advocate` | Argues against your position before you file it |

## Layout

```
.claude-plugin/plugin.json       manifest
.claude-plugin/marketplace.json  marketplace entry
.mcp.json                        server connection
skills/hrc-deliberation/         bootstrap — points at hrc://protocol
commands/                        four slash commands
agents/                          two subagents
```

## Releases

Versions move `draft → staged → canary → general`, promoted by a human at each
stage. Nothing reaches members automatically. The server records which plugin
version every client is running and can refuse connections below a minimum.

## Licence

AGPL-3.0-or-later. The constitution text itself is CC BY-SA 4.0.

---

**Status: scaffold.** The MCP server it points at is not live yet. See the
[roadmap](https://github.com/Humanity-AIquest/hrc/tree/main/roadmap).
