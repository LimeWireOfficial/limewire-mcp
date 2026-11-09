# Installing LimeWire MCP (for AI agents such as Cline)

LimeWire MCP is a **hosted remote server**. There is nothing to clone, build or run locally.

1. Add this entry to the MCP settings file (in Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "limewire": {
      "type": "streamableHttp",
      "url": "https://mcp.limewire.com/mcp",
      "disabled": false
    }
  }
}
```

`"type": "streamableHttp"` is required. Without it Cline falls back to the legacy SSE transport and the connection fails.

2. Save the file. The server answers `401` with OAuth metadata and the client opens a LimeWire sign-in page in the browser. A free LimeWire account is enough. The client registers itself automatically (dynamic client registration) — no client id or secret is needed.

3. After sign-in the server exposes 17 tools: upload, download, list, share by link, scratch space and more. If the browser sign-in does not open on its own, ask the user to click "Authenticate" next to the server in the MCP Servers panel.

## Without a browser (headless agents)

If you already have a LimeWire agent key, send it as a header instead of OAuth:

```json
{
  "mcpServers": {
    "limewire": {
      "type": "streamableHttp",
      "url": "https://mcp.limewire.com/mcp",
      "headers": { "Authorization": "Bearer <AGENT_KEY>" }
    }
  }
}
```

Use one key per agent and never commit it to a repository.
