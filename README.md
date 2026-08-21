# Nomas Research MCP

Hosted [Model Context Protocol](https://modelcontextprotocol.io) server for [Nomas](https://nomas.fyi): parsed SEC events keyed by CIK and CUSIP — 8-K items, Form 144, Form D, FTD. Not ticker quotes. Not EDGAR HTML.

- Endpoint: `https://mcp.nomas.fyi/mcp` (Streamable HTTP)
- Registry: [`io.github.carterchencc/nomas`](https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.carterchencc/nomas)
- Docs: [nomas.fyi/research/mcp](https://nomas.fyi/research/mcp)

This public repo is the registry + Cursor plugin package (manifest, MCP URL, logo). It is not the Nomas product source.

## What it does

Read-only tools. Tickers are reused; start with `lookup_issuer` (CIK + live CUSIPs). Then:

- Mixed issuer tape: parsed 8-K items, Form 144 proposed sales, Form D, 13D, periodic, proxy, offerings
- FTD series by CUSIP (do not collapse CUSIPs)
- XBRL company facts, Form 4 insider trades, 13F-by-manager when those datasets are the question

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
