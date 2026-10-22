# MrScraper for Gemini CLI

MrScraper connects [Gemini CLI](https://geminicli.com) to a hosted MCP server
for retrieving public web pages as HTML, Markdown, or screenshots, Google
discovery, and account usage. The extension also includes three focused skills
that help Gemini choose the right workflow and preserve raw page content.

## What this extension adds

- The hosted Streamable HTTP endpoint at `https://mcp.mrscraper.com/mcp`.
- OAuth 2.1 sign-in through Gemini CLI's MCP client; no credential is stored in
  this repository.
- The `mrscraper`, `mrscraper-fetch`, and `mrscraper-serp` agent skills and a
  short `GEMINI.md` context file.

## Requirements

- A current version of [Gemini CLI](https://geminicli.com/docs/get-started/).
- A [MrScraper](https://app.mrscraper.com) account.
- Permission to access and process the target content.

## Install

```bash
gemini extensions install https://github.com/mrscraper-com/mrscraper-gemini-extension
```

## Sign in

Start `gemini` and run:

```text
/mcp auth mrscraper
```

Gemini CLI opens the MrScraper consent page in your browser; sign in and
approve access. Gemini CLI registers its own OAuth client with MrScraper, so
there is no API key to copy. Never paste OAuth tokens or API keys into chat.

Until you sign in, `gemini mcp list` shows `mrscraper` as `Disconnected`.

## Try it

```text
Fetch https://www.scrapethissite.com/pages/simple/ as Markdown and list the five countries with the largest area.
```

| Tool | Purpose |
| --- | --- |
| `scraperAPI` | Retrieve a known page as HTML, Markdown, a screenshot, or a combination. |
| `webSearch` | Discover public pages through Google. |
| `status` | Inspect subscription status, token usage, and remaining tokens. |

## Data and permissions

The extension sends MCP tool inputs, including target URLs and search queries,
to MrScraper's hosted service. Page responses and tool results are then
available to Gemini for the requested task. Use it only with public or
otherwise authorized content, and follow the target site's requirements.

- `https://mcp.mrscraper.com/mcp`: the hosted MCP server. Tool inputs are sent
  here.
- `https://api.app.mrscraper.com`: the OAuth 2.1 authorization server,
  advertised in the server's protected resource metadata.
- `https://app.mrscraper.com`: the MrScraper sign-in and consent pages opened in
  your browser.

Review MrScraper's [MCP documentation](https://docs.mrscraper.com/docs/getting-started/mcp-server),
[Privacy Policy](https://mrscraper.com/privacy-policy), and
[Acceptable Use Policy](https://mrscraper.com/acceptable-use-policy) before use.

## Update or remove

```bash
gemini extensions update mrscraper
gemini extensions uninstall mrscraper
```

## Support and security

- Product help: [MrScraper MCP documentation](https://docs.mrscraper.com/docs/getting-started/mcp-server)
- Bugs and feature requests: [GitHub Issues](https://github.com/mrscraper-com/mrscraper-gemini-extension/issues)
- Account help: [support@mrscraper.com](mailto:support@mrscraper.com)
- Security reports: see [SECURITY.md](SECURITY.md)

## Development

Validate and install from a local checkout:

```bash
gemini extensions validate .
gemini extensions install . --consent
gemini extensions list
```

The skills in `skills/` are kept identical to the MrScraper Claude plugin.

## License

[MIT](LICENSE)
