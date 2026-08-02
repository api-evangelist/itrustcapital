# iTrustCapital

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
