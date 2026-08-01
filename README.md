# Ather Energy

Ather Energy Limited is a Bengaluru-based Indian electric two-wheeler manufacturer founded in 2013 by Tarun Mehta and Swapnil Jain. It builds connected electric scooters — the Ather 450 series (450S, 450X, 450 Apex) and the family-oriented Rizta — around AtherStack, its proprietary in-house vehicle software architecture delivered over the air, and operates Ather Grid, India's largest two-wheeler fast-charging network.

- https://www.atherenergy.com/
- https://github.com/AtherEnergy

## API surface

Ather publishes **no developer API** — no OpenAPI, Swagger, GraphQL, AsyncAPI, gRPC or webhook contract exists on any Ather host, and no `developer.`/`docs.`/`api.` subdomain resolves.

The one machine-callable surface is on the commerce host: `shop.atherenergy.com` advertises a
[Universal Commerce Protocol](https://ucp.dev) merchant profile at `/.well-known/ucp` declaring an **MCP
shopping endpoint** at `https://shop.atherenergy.com/api/ucp/mcp`. Anonymous `tools/list` is refused
(HTTP 422, `invalid_profile_url`) — a registered UCP agent profile is required. The server is provided by
the Shopify platform; the merchant profile, catalog, payment handlers and host are Ather's.

Ather also publishes a curated `/llms.txt` on the corporate host and a `robots.txt` that explicitly allows
GPTBot, ChatGPT-User, Google-Extended, ClaudeBot and PerplexityBot while blocking CCBot.

## Artifacts

| Dir | What |
|---|---|
| `llms/` | Corporate `llms.txt`, plus the Ather Shop `llms.txt` and `agents.md` (all verbatim) |
| `well-known/` | Well-known probe index + the verbatim UCP merchant profile |
| `mcp/` | The Ather Shop UCP/MCP shopping service manifest |
| `agentic-access/` | Published agent-execution contract (human-in-the-loop on checkout) |
| `conventions/` | Runtime semantics for the UCP/MCP surface — versioning, rate limits, error envelope |
| `conformance/` | Standards Ather does and does not conform to |
| `packages/` | First-party open-source packages (no API client SDKs — there is no API) |
| `security/` | Domain security probe + the Responsible Vulnerability Disclosure Program |
