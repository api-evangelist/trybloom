# Bloom

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Bloom (trybloom.ai) is the brand layer for agents — a Y Combinator (Spring 2026) company founded by Ray Fitzgerald that turns a brand into infrastructure any agent, app, or platform can call. Point Bloom at a website or Instagram profile and it ingests the brand — logo, palette, type, tone, visual DNA — then generates on-brand images (edit, resize, background removal, vectorize to SVG, 2K/4K, variants) through a web app, a credit-priced REST API with a live OpenAPI 3.1 contract, and an official hosted MCP server with OAuth sign-in for Claude, ChatGPT, Cursor, and other agents.

**Areas:** Company · Brand Management · Image Generation · Artificial Intelligence · Agents · MCP · Marketing · Creative

## Bloom on APIs.io

Everything profiled for Bloom is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/trybloom/](https://apis.io/providers/trybloom/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [Bloom Account API](https://apis.io/apis/trybloom/trybloom-account-api/) — Inspect the authenticated account — profile, credit balance, and accessible workspaces.
- [Bloom Brands API](https://apis.io/apis/trybloom/trybloom-brands-api/) — Manage brands and brand identity.
- [Bloom Images API](https://apis.io/apis/trybloom/trybloom-images-api/) — Generate, edit, and retrieve images.
- [Bloom Audio API](https://apis.io/apis/trybloom/trybloom-audio-api/) — Retrieve and manage audio files.
- [Bloom Briefs API](https://apis.io/apis/trybloom/trybloom-briefs-api/) — Get brand guidance and selected assets for a specific task.
- [Bloom Feedback API](https://apis.io/apis/trybloom/trybloom-feedback-api/) — Report problems and observations about Rainbrand.
- [Bloom Generations API](https://apis.io/apis/trybloom/trybloom-generations-api/) — Create and retrieve model generations.
- [Bloom Library API](https://apis.io/apis/trybloom/trybloom-library-api/) — Add, list, and remove a brand's images, video, and audio.
- [Bloom Models API](https://apis.io/apis/trybloom/trybloom-models-api/) — Find available models and check their inputs.
- [Bloom Reviews API](https://apis.io/apis/trybloom/trybloom-reviews-api/) — Check an asset against a brand's color, typography, logo, and copy guidance.
- [Bloom Uploads API](https://apis.io/apis/trybloom/trybloom-uploads-api/) — Stage private local files for brand sources, the Library, and other supported operations.
- [Bloom Videos API](https://apis.io/apis/trybloom/trybloom-videos-api/) — Retrieve and manage video files.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [bloom](https://apis.io/servers/trybloom/bloom/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Trybloom Agentic Access](https://apis.io/agentic-access/trybloom/trybloom-agentic-access/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Trybloom Context](https://apis.io/jsonld/trybloom/trybloom-context/)

#### Collections (3)

Postman and Open Collection request collections.

- [Bloom Account API](https://apis.io/collections/trybloom/open-trybloom-account-api/)
- [Bloom Brands API](https://apis.io/collections/trybloom/open-trybloom-brands-api/)
- [Bloom Images API](https://apis.io/collections/trybloom/open-trybloom-images-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Trybloom Api Overlay](https://apis.io/overlays/trybloom/trybloom-api-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Bloom API Rules](https://apis.io/rules/trybloom/trybloom-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Trybloom Authentication](https://apis.io/security/trybloom/trybloom-authentication/)
- [Trybloom Domain Security](https://apis.io/security/trybloom/trybloom-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Trybloom Scopes](https://apis.io/scopes/trybloom/trybloom-scopes/)

#### Plans and pricing (2)

Published plans, tiers and prices.

- [Trybloom Plans Pricing](https://apis.io/plans/trybloom/trybloom-plans-pricing/)
- [Trybloom Price Estimates](https://apis.io/plans/trybloom/trybloom-price-estimates/)

#### Rate limits (1)

Published request limits.

- [Trybloom Rate Limits](https://apis.io/rate-limits/trybloom/trybloom-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Trybloom Finops](https://apis.io/finops/trybloom/trybloom-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.trybloom.ai/)
- [Documentation](https://www.trybloom.ai/docs/api)
- [Getting started](https://www.trybloom.ai/docs/api)
- [API reference](https://www.trybloom.ai/docs/api-reference/account/get-account)
- [Pricing](https://www.trybloom.ai/pricing/)
- [Sign up](https://www.trybloom.ai/auth/sign-up)
- [Support](https://discord.gg/rncVAMSQ9f)
- [Changelog](https://www.rainbrand.com/changelog/)
- [Blog](https://www.rainbrand.com/blog/)
- [Terms of service](https://www.trybloom.ai/terms/)
- [Privacy policy](https://www.trybloom.ai/privacy/)
- [GitHub](https://github.com/trybloomai)

## API Evangelist rating

**Kin Score 52.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 49.0 |
| Contract governance | 4.5 |
| Operational transparency | 39.5 |
| Developer ergonomics | 52.4 |
| Access clarity | 76.3 |

**Agent readiness 50.0** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 31.8** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/trybloom/](https://apis.io/providers/trybloom/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Bloom: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/trybloom/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
