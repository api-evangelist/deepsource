# DeepSource (deepsource)

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
