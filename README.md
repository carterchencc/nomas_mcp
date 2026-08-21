# Nomas Research MCP

Hosted [Model Context Protocol](https://modelcontextprotocol.io) server for [Nomas](https://nomas.fyi): structured SEC data, not raw EDGAR HTML.

- Endpoint: `https://mcp.nomas.fyi/mcp` (Streamable HTTP)
- Registry: [`io.github.carterchencc/nomas`](https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.carterchencc/nomas)
- Docs: [nomas.fyi/research/mcp](https://nomas.fyi/research/mcp)

This public repo is the registry + Cursor plugin package (manifest, MCP URL, logo). It is not the Nomas product source.

## What it does

Read-only tools for:

- Company search and detail
- XBRL company facts
- Parsed filings (8-K, 10-K/Q, 13D, 144, D, 14A, S-1/S-3)
- Insider trades (Forms 3/4/5)
- 13F managers and holdings
- Failure-to-deliver (FTD)

## Install

1. Install **Nomas Research** from the [Cursor Marketplace](https://cursor.com/marketplace), or clone this repo and load it from `~/.cursor/plugins/local` while testing.
2. Create a named API key at [nomas.fyi/AccountManagement](https://nomas.fyi/AccountManagement).
3. In Cursor, open **Plugins → Configure** and set **Nomas API key**. Do not put the key in this repo.

Manual MCP (without the plugin):

```json
{
  "mcpServers": {
    "nomas": {
      "url": "https://mcp.nomas.fyi/mcp",
      "headers": { "X-API-Key": "YOUR_API_KEY" }
    }
  }
}
```

Docs: [nomas.fyi/research/mcp](https://nomas.fyi/research/mcp)  
Privacy: [nomas.fyi/privacy](https://nomas.fyi/privacy)

Free, Pro, and API plan limits on nomas.fyi still apply.

## Layout

```
server.json                  Official MCP Registry metadata
.cursor-plugin/plugin.json   Cursor marketplace manifest
mcp.json                     Streamable HTTP MCP endpoint
assets/logo.png              Marketplace logotype
skills/nomas-sec-research    When to call which tools
```

## Official MCP Registry

Metadata is in `server.json` (`io.github.carterchencc/nomas`). Publish with:

```bash
mcp-publisher login github
mcp-publisher publish
```

## License


MIT for this plugin package. Nomas data and the hosted server remain a Nomas service.
