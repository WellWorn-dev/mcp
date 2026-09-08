# Wellworn MCP server

Remote endpoint: `https://mcp.wellworn.dev/mcp` (Streamable HTTP, stateless). Works without a key: 60 calls a day per IP. A free key raises that to 2,000 a month per organization.

## Tools

| Tool | What it returns |
|---|---|
| `recommend` | pick, alternative and when it wins, avoid, traps, skill, provenance; under 800 tokens |
| `compare` | the same block for 2 to 4 named options |
| `alternatives` | open-source or self-hosted alternatives to a SaaS or library |
| `traps` | known breakages for a library at a version; pass `id` for the full fix |
| `skill` | the SKILL.md procedure or its install command |
| `design` | design system, tokens, layout rules, anti-patterns for a screen |
| `docs` | official docs URL, llms.txt, latest version |
| `submit_trap` | report a breakage and its fix to a reviewer (needs a key) |

## Install

Claude Code:

```
claude mcp add --transport http wellworn https://mcp.wellworn.dev/mcp
```

Cursor, Codex CLI, Gemini CLI, Windsurf, Cline, Zed, VS Code: https://wellworn.dev/docs

With a key, send `Authorization: Bearer ww_...`.

## Source

The server is TypeScript on `@modelcontextprotocol/sdk` 1.x, Express, Postgres, and Redis. Source is published here from the Wellworn monorepo on each release. License: MIT.
