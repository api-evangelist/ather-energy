# Ather Energy

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
