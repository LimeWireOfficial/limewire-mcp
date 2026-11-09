# LimeWire MCP

<img src="assets/logo.png" alt="LimeWire" width="96" align="right">

Hosted file storage for AI agents. Upload, list, download, share by link, expire and use scratch space - from Claude, Cursor, VS Code, Codex, Gemini CLI or any other MCP client.

- **Server URL:** `https://mcp.limewire.com/mcp` (Streamable HTTP)
- **Auth:** sign in with your LimeWire account (OAuth, dynamic client registration), or send an agent key as `Authorization: Bearer <key>` - one key per agent
- **Docs and plans:** <https://limewire.com/mcp>
- **Registry:** [`com.limewire/agent-files`](https://registry.modelcontextprotocol.io/?q=com.limewire/agent-files) in the Official MCP Registry
- **Claude:** [Connectors Directory](https://claude.ai/directory/connectors/limewire-agent-files)

This repository holds only the client manifests. The server itself is hosted by LimeWire; there is nothing to run locally.

## Install

| Client | How |
|---|---|
| Claude Code | `claude mcp add --transport http limewire https://mcp.limewire.com/mcp` |
| Claude Desktop / claude.ai | Add from the [Connectors Directory](https://claude.ai/directory/connectors/limewire-agent-files) |
| Cursor | `.cursor/mcp.json`: `{ "mcpServers": { "limewire": { "url": "https://mcp.limewire.com/mcp" } } }` |
| VS Code | `{ "servers": { "limewire": { "type": "http", "url": "https://mcp.limewire.com/mcp" } } }`, or search `@mcp limewire` in Extensions |
| Cline | MCP Servers → Remote Servers: URL `https://mcp.limewire.com/mcp`, transport **Streamable HTTP**; details in [`llms-install.md`](llms-install.md) |
| Gemini CLI | `gemini extensions install https://github.com/LimeWireOfficial/limewire-mcp` |
| Codex / any Agent Plugins client | this repository is an [Agent Plugin](https://agent-plugins.org): `plugin.json` + `mcp.json` |
| Anything else | point a remote MCP client at `https://mcp.limewire.com/mcp` |

The first call opens a LimeWire sign-in; a free account is enough to try every tool.

## Tools

17 tools: upload (direct, or presigned and multipart for large files), download, list, stat, delete, share by link, usage and quota, retention get/set, and a per-agent scratch area (put, get, list, clear). Destructive tools are annotated as such so clients can ask before running them.

## Free plan

1 GiB storage, 100 MiB per file, 200 uploads and 50 share links per day, share links live up to 24 hours, files are kept for 7 days. Paid plans: <https://limewire.com/pricing>.

## Support

support@limewire.com - [Terms](https://limewire.com/terms) - [Privacy](https://limewire.com/privacy)
