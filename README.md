# iTrustCapital

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

iTrustCapital (legal entity **ITC2.0, Inc.**) is a US fintech software platform for alternative assets,
offering 24/7 self-directed access to dozens of cryptocurrencies and physical precious metals through
tax-advantaged Crypto IRAs, Premium Custody Accounts (PCA), and Treasury Accounts for businesses, trusts
and non-profits. It charges a 1% cryptocurrency transaction fee with no monthly, annual, startup, exit,
storage or transfer fees.

- Website: https://www.itrustcapital.com/
- Secondary market listing: https://forgeglobal.com/itrustcapital_stock/

## API surface: none

**iTrustCapital publishes no public developer API.** Its own help center states:

> "At this time iTrustCapital does not offer any API integration to any third-party applications,
> including self-trading bots and coin trackers."
> — [Does iTrustCapital offer API integrations to third party platforms?](https://help.itrustcapital.com/hc/en-us/articles/4411749720083-Does-iTrustCapital-offer-API-integrations-to-third-party-platforms)

Full STEP 0b contract discovery was run before recording that (OpenAPI on every host root, DNS
enumeration of API subdomains, GraphQL, MCP `tools/list`, A2A agent card on both the canonical and
legacy well-known paths, npm/PyPI, and the GitHub org). Every probe and its HTTP status is recorded in
[`well-known/itrustcapital-well-known.yml`](well-known/itrustcapital-well-known.yml).

Two traps worth noting for any re-run:

1. The marketing site (Next.js) answers **HTTP 200 with the SPA HTML shell for every unknown path** —
   including `/openapi.json`, `/llms.txt` and every `/.well-known/*` path. Those 200s are catch-all
   false positives, not documents. Check `Content-Type` before trusting them.
2. `app.itrustcapital.com` is behind Cloudflare bot management and returns **403** to anonymous probes.

## Artifacts

| Artifact | Method | Notes |
|---|---|---|
| [`well-known/itrustcapital-well-known.yml`](well-known/itrustcapital-well-known.yml) | probed | Full contract-discovery record; no well-known documents published |
| [`security/itrustcapital-domain-security.yml`](security/itrustcapital-domain-security.yml) | probed | TLS 1.3, HSTS, DNSSEC, CAA (6 issuers), SPF, DMARC `p=reject` |
| [`lifecycle/itrustcapital-lifecycle.yml`](lifecycle/itrustcapital-lifecycle.yml) | searched | First-party service-status page; no API versioning/deprecation (no API) |
| [`llms/itrustcapital-llms.txt`](llms/itrustcapital-llms.txt) | generated | Generated from the provider's own public pages; no `/llms.txt` is published |

No vulnerability disclosure program, trust center, published certifications, SDKs, CLI, MCP server,
A2A agent card, webhooks or AsyncAPI surface were found.
