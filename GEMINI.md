# MrScraper

The `mrscraper` MCP server retrieves public web pages and Google results
through MrScraper's hosted service:

- `scraperAPI`: retrieve a known URL as HTML, Markdown, a screenshot, or a
  combination.
- `webSearch`: search Google from query text or a Google search URL. Use
  `raw=false` and `format=json` for parsed results.
- `status`: show the connected account's plan, token usage, and remaining
  tokens.

The `mrscraper`, `mrscraper-fetch`, and `mrscraper-serp` skills describe when
to use each tool. For a known URL, retrieve the page first and work from the
raw response; use search only when the URL is unknown.

Authentication is OAuth 2.1 on the MCP connection. If a tool reports that
sign-in is required, ask the user to run `/mcp auth mrscraper`. Never ask for,
print, or pass API keys or tokens as tool arguments.

Every request uses the user's MrScraper plan. Use MrScraper only for public or
otherwise authorized content.
