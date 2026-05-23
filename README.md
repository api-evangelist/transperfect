# TransPerfect

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
