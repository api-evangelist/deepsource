# DeepSource (deepsource)

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

DeepSource is a code-quality and security platform that performs static analysis, SCA, secrets detection, AI code review, and Autofix across repositories. Its developer platform is a GraphQL API at https://api.deepsource.com/graphql/ exposing repositories, analysis runs, issues, checks, analyzers, and quality-gate management, authenticated with a Personal Access Token Bearer credential.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/deepsource/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/deepsource/refs/heads/main/apis.yml)

## Tags

- Code Quality
- Static Analysis
- Code Review
- Security
- GraphQL

## Timestamps

- **Created:** 2026-06-21
- **Modified:** 2026-06-21

## APIs

### DeepSource Repositories API

GraphQL queries and mutations over the `repository` and `account` root fields - fetch repository metadata, DSN, default branch, activation state, enabled analyzers, and activate/deactivate analysis or update default branch.

- **Human URL:** [https://docs.deepsource.com/docs/developers/api/repository](https://docs.deepsource.com/docs/developers/api/repository)
- **Base URL:** `https://api.deepsource.com/graphql`

#### Tags

- Repositories
- GraphQL
- Configuration

#### Properties

- [Documentation](https://docs.deepsource.com/docs/developers/api)
- [API Reference](https://docs.deepsource.com/docs/developers/api/repository)
- [GraphQL](graphql/deepsource-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/deepsource-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deepsource.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deepsource.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### DeepSource Issues API

GraphQL access to detected issues, issue occurrences, dependency vulnerability (SCA) occurrences, ignore rules, and team-level issue suppression across a repository's analysis results.

- **Human URL:** [https://docs.deepsource.com/docs/developers/api/schema](https://docs.deepsource.com/docs/developers/api/schema)
- **Base URL:** `https://api.deepsource.com/graphql`

#### Tags

- Issues
- Occurrences
- GraphQL

#### Properties

- [Documentation](https://docs.deepsource.com/docs/developers/api)
- [API Reference](https://docs.deepsource.com/docs/developers/api/schema)
- [GraphQL](graphql/deepsource-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/deepsource-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deepsource.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deepsource.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### DeepSource Runs and Checks API

GraphQL queries over the `run` root field and a repository's `analysisRuns` - fetch analysis runs by UID or commit SHA, their per-analyzer checks, status, and introduced/resolved issue counts.

- **Human URL:** [https://docs.deepsource.com/docs/developers/api/schema](https://docs.deepsource.com/docs/developers/api/schema)
- **Base URL:** `https://api.deepsource.com/graphql`

#### Tags

- Runs
- Checks
- Analysis
- GraphQL

#### Properties

- [Documentation](https://docs.deepsource.com/docs/developers/api)
- [API Reference](https://docs.deepsource.com/docs/developers/api/schema)
- [GraphQL](graphql/deepsource-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/deepsource-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deepsource.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deepsource.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### DeepSource Analyzers API

GraphQL queries over the `analyzer`/`analyzers` and `codeFormatter`/`codeFormatters` root fields - list available analyzers and code formatters, their metadata, shortcodes, and supported transformers.

- **Human URL:** [https://docs.deepsource.com/docs/developers/api/schema](https://docs.deepsource.com/docs/developers/api/schema)
- **Base URL:** `https://api.deepsource.com/graphql`

#### Tags

- Analyzers
- Code Formatters
- Transformers
- GraphQL

#### Properties

- [Documentation](https://docs.deepsource.com/docs/developers/api)
- [API Reference](https://docs.deepsource.com/docs/developers/api/schema)
- [GraphQL](graphql/deepsource-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/deepsource-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/deepsource.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/deepsource.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/deepsourcecorp)
- [LinkedIn](https://www.linkedin.com/company/deepsource)
- [Website](https://deepsource.com)
- [Documentation](https://docs.deepsource.com/docs/developers/api)
- [Plans](plans/deepsource-plans-pricing.yml)
- [Rate Limits](rate-limits/deepsource-rate-limits.yml)
- [Fin Ops](finops/deepsource-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
