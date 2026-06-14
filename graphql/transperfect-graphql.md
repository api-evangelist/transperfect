# TransPerfect GraphQL

## Description

TransPerfect does not currently publish a native GraphQL API. Their public-facing API surface consists of the GlobalLink Strings REST API (formerly Applanga) at `https://api.globallinkstrings.com/v1/api`, with no GraphQL endpoint documented in their developer resources, GitHub organizations (TransPerfect, applanga), or corporate documentation portal as of June 2026.

The schema in `transperfect-schema.graphql` is a conceptual GraphQL representation of the TransPerfect/GlobalLink translation and localization data model, derived from:

- GlobalLink Strings REST API documentation at https://www.applanga.com/docs/integration-documentation/api
- GlobalLink platform module descriptions (TMS, Web, Portal, Now, Strings, CCMS, Media)
- TransPerfect service catalog (translation, localization, interpretation, AI/MT)
- Standard translation-industry data entities (TMX, XLIFF, glossaries, termbases, language pairs)

## Endpoint / Documentation URLs

| Resource | URL |
|----------|-----|
| GlobalLink Strings API reference | https://www.applanga.com/docs/integration-documentation/api |
| GlobalLink Strings docs | https://www.applanga.com/docs |
| TransPerfect main site | https://www.transperfect.com/ |
| GlobalLink suite | https://globallink.transperfect.com/ |
| GitHub (TransPerfect org) | https://github.com/TransPerfect |
| GitHub (Applanga/Strings org) | https://github.com/applanga |

## Notes on GraphQL Support

- No GraphQL endpoint is published for any GlobalLink module (TMS, Web, Portal, CCMS, Now, Media, Live, TV, Share, Scribe, Voice, Translate & Review, Write, or Tower LLM).
- The GlobalLink Strings API is REST-only, using Bearer Token authentication (`Authorization: Bearer <apiToken>` + `X-Personal-Access-Token` header for write operations).
- TransPerfect's 100+ pre-built connectors use REST and file-exchange protocols (XLIFF, TMX, Android XML, iOS .strings, PO, etc.), not GraphQL.
- GlobalLink does expose a webhooks resource (event-driven callbacks), but no GraphQL subscriptions or schema registry is documented.
- The conceptual schema below models the core translation workflow entities that would be natural candidates for a GraphQL API, covering projects, jobs, language pairs, glossaries, translation memories, quality scoring, and human reviewer assignments.
- Source: conceptual data model derived from REST API documentation and GlobalLink platform feature descriptions.
