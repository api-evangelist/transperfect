# TransPerfect

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

This repository indexes TransPerfect, the world's largest privately held provider of language and AI services, with 2025 billed revenues of $1.32 billion (+7% YoY), 160+ global offices, 30+ years in business, 10,000+ clients including 90% of the Fortune 500, and the 6,000-organization GlobalLink platform footprint. TransPerfect was founded in 1992, is headquartered in New York, and is led by President and CEO Phil Shawe with Co-CEO Jin Lee.

The corporate positioning, drawn verbatim from transperfect.com: "Intelligent Performance: However you define success, TransPerfect delivers it with technology and expertise — any market, any language."

## Why this repo is thin

TransPerfect is a sales-led services and technology company without a unified developer portal. The only public REST API with documented endpoints, authentication, SDKs, and a CLI is **GlobalLink Strings** (formerly Applanga, retained as `api.globallinkstrings.com/v1/api`). The flagship GlobalLink TMS, Web, Portal, CCMS, Now, Media, Live, TV, Share, Scribe, Voice, Translate & Review, Write, and Tower LLM modules are described as enterprise platforms with "100+ pre-built connectors with a conversational MCP interface" — but none publish an OpenAPI specification, public reference, or self-service developer onboarding. MediaNEXT has no public technical surface. The TransPerfect/globallink GitHub repository (a Drupal connector) has not been updated since 2016.

This repo documents what is public and flags the absences rather than fabricating specs that do not exist.

## Index

- [apis.yml](./apis.yml) — Primary index covering the GlobalLink Strings API, the legacy Drupal connector, the full 15-module GlobalLink suite, the broader service catalog, leadership, scale numbers, and the recent acquisition cadence (Unbabel, Omnimago, Studio Emme, Semantix).
- [vocabulary/transperfect-vocabulary.yml](./vocabulary/transperfect-vocabulary.yml) — Controlled vocabulary across language services, the GlobalLink suite, translation workflow primitives, the GlobalLink Strings API resource model, AI/data services, and industry verticals.
- [json-ld/transperfect-context.jsonld](./json-ld/transperfect-context.jsonld) — JSON-LD context mapping TransPerfect and GlobalLink terms to schema.org and a TransPerfect namespace.
- [json-schema/transperfect-translation-entry-schema.json](./json-schema/transperfect-translation-entry-schema.json) — JSON Schema for a GlobalLink Strings translation entry, including key, locale, value, plural forms, status, tags, screenshot references, and audit fields.
- [json-structure/transperfect-translation-entry-structure.json](./json-structure/transperfect-translation-entry-structure.json) — JSON Structure variant of the same entity for structure-aware tooling.

## Public surface documented

### GlobalLink Strings API

- Base URL: `https://api.globallinkstrings.com/v1/api` (legacy `https://api.applanga.com/v1/api` deprecated)
- Authentication: `Authorization: Bearer {apiToken}` plus `X-Personal-Access-Token` for write operations; `app={app_id}` query parameter identifies the project (prefix of the API token before the `!`); optional `branch={branch_id}`
- Resources: Entries, Languages, Tags, Screenshots, Projects, Branches, Orders, Webhooks
- Limits: 50 MB max body, optional GZIP via `Accept-Encoding`
- File formats: 25+ including Android XML, iOS `.strings`/`.stringsdict`, JSON (nested, React, Angular), YAML, CSV, XLIFF, PO, properties
- SDKs: iOS, Android, Unity, SwiftUI, React Native, Flutter — all published under `github.com/applanga`
- CLI: `applanga` (Python), installable via Homebrew (`brew tap applanga/cli && brew install applanga`) or binary release; supports `init`, `push`, `pull`, `pushtarget`, `pullsource` with `--draft`, `--force`, `--tag`, `--languages` flags
- CI/CD: GitHub Action via `applanga/setup-applanga-cli`

### GlobalLink Drupal Connector

- Repo: `github.com/TransPerfect/globallink`
- Language: PHP (Drupal module)
- Status: Last meaningful update 2016; documented here for completeness but treated as legacy

## GlobalLink suite (no public REST/OpenAPI)

GlobalLink TMS, GlobalLink Web, GlobalLink Portal, GlobalLink Now, GlobalLink Strings, GlobalLink CCMS, GlobalLink Media, GlobalLink Live, GlobalLink TV, GlobalLink Share, GlobalLink Scribe, GlobalLink Voice, GlobalLink Translate & Review, GlobalLink Write, Tower LLM. GlobalLink won 24 G2 awards across 12 categories in May 2026.

## Other TransPerfect platforms

DataForce (AI training data and annotation), Trial Interactive (eClinical), Vasont CCMS, Reef (eDiscovery; Reef Review 4.0 added AI-enabled review in March 2026), MediaNEXT (broadcast localization), TransPerfect Legal, TransPerfect Life Sciences, TransPerfect Games, Semantix (acquired Nordic LSP), Unbabel (acquired August 2026).

## Notable absences

- No unified developer portal at transperfect.com.
- No public OpenAPI / Swagger / Postman collection for any GlobalLink module, despite GlobalLink Strings exposing a documented REST API.
- No public webhook event schema or AsyncAPI document despite the Webhooks resource.
- No public pricing pages; commercial engagement runs through sales.
- No public status page indexed.
- No RSS feed surfaced on the corporate blog.
- TransPerfect's primary GitHub org has one public repository (PHP, 2016).

## Sources

- https://www.transperfect.com/
- https://www.transperfect.com/about/leadership
- https://www.transperfect.com/news
- https://www.transperfect.com/blog
- https://globallink.transperfect.com/
- https://globallink.transperfect.com/products
- https://globallink.transperfect.com/products/globallink-tms
- https://www.applanga.com/docs
- https://www.applanga.com/docs/integration-documentation/api
- https://www.applanga.com/docs/integration-documentation/cli
- https://github.com/TransPerfect
- https://github.com/TransPerfect/globallink
- https://github.com/applanga
