---
name: nomas-sec-research
description: Look up structured SEC data with Nomas MCP tools. Use when the user asks for company facts, parsed filings, insider trades, 13F holdings, or failure-to-deliver.
---

Use the Nomas MCP tools. Do not invent CIKs, CUSIPs, accessions, or numbers.

1. Resolve the company with `search_company`, then `get_company_detail` if needed.
2. Company facts: `list_concepts` then `get_company_facts` (include dates, units, quarterly vs annual).
3. Filings: `list_parsed_filings` by family (`8k`, `periodic`, `13d`, `144`, `d`, `proxy`, `offering`), then `get_parsed_filing` by accession.
4. Ownership: `get_insider_trades`, `search_13f_managers` / `get_13f_holdings`, `get_ftd` by CUSIP.
5. Quote accessions and identifiers from tool results. Do not file, trade, or give personalized investment advice.
