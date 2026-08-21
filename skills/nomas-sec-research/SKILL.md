---
name: nomas-sec-research
description: Look up hosted parsed SEC events with Nomas MCP. Use for 8-K items, Form 144, Form D, FTD by CUSIP, not ticker quotes or raw EDGAR HTML.
---

Use the Nomas MCP tools. Do not invent CIKs, CUSIPs, accessions, or numbers. Tickers are reused.

1. Start with `lookup_issuer` (name or ticker) for CIK plus live FTD CUSIPs. Never guess a CUSIP. `search_ftd` if the question is CUSIPs only.
2. Mixed issuer tape: `list_parsed_filings` without family, passing `ciks`. These are hosted parsed headlines (8-K items, Form 144 amounts, Form D, 13D, periodic, proxy, offerings), not EDGAR HTML. `get_parsed_filing` for child tables.
3. `get_ftd` only after a CUSIP is chosen from `lookup_issuer` or `search_ftd`.
4. XBRL (`list_concepts` / `get_company_facts`), Form 4 (`get_insider_trades`), and 13F-by-manager only if the question is explicitly those datasets.
5. Quote accessions and identifiers from tool results. Do not file, trade, or give personalized investment advice.
