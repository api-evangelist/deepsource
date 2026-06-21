# DeepSource GraphQL API

The [DeepSource](https://deepsource.com) developer platform is a single **GraphQL API**
that exposes repositories, analysis runs, issues, checks, analyzers, code formatters,
and quality-gate management for the DeepSource code-quality and security platform.

- API docs: <https://docs.deepsource.com/docs/developers/api>
- Schema overview: <https://docs.deepsource.com/docs/developers/api/schema>
- Repository quickstart: <https://docs.deepsource.com/docs/developers/api/repository>
- GitHub org: <https://github.com/deepsourcecorp>

---

## Transport

DeepSource exposes a single GraphQL endpoint. All operations are sent as an HTTP
`POST` with a JSON body containing `query` and optional `variables`.

| Property | Value |
|----------|-------|
| Endpoint (Cloud) | `https://api.deepsource.com/graphql/` |
| Legacy endpoint | `https://api.deepsource.io/graphql/` (older host; the `.com` host is canonical) |
| On-premise | `https://<hostname>/api/graphql/` |
| Method | `POST` |
| Content-Type | `application/json` |
| Auth | `Authorization: Bearer <PERSONAL_ACCESS_TOKEN>` |

A Personal Access Token (PAT) is generated from the DeepSource dashboard and passed
as a Bearer credential. There is no GraphQL subscription transport documented; the
API is query/mutation over HTTP only.

### Example request

```bash
curl 'https://api.deepsource.com/graphql/' \
  -X POST \
  -H 'Authorization: Bearer <PERSONAL_ACCESS_TOKEN>' \
  -H 'accept: application/json' \
  -H 'content-type: application/json' \
  --data '{ "query": "query { viewer { email } }" }'
```

---

## Schema file

See [`deepsource-schema.graphql`](./deepsource-schema.graphql) for a representative
SDL. The SDL is a hand-written, **representative** subset of the DeepSource schema
modeling the documented root fields, connections, and mutations — it is not the
provider's machine-generated introspection schema and field sets are illustrative.

---

## Root query fields

| Field | Purpose |
|-------|---------|
| `viewer` | The authenticated user's profile and accounts |
| `account(login, vcsProvider)` | A team or individual DeepSource account |
| `repository(name, login, vcsProvider)` | A repository and its analysis data |
| `run(runUid)` / runs by commit | An analysis run by UID or commit SHA |
| `analyzer` / `analyzers` | One or all code analyzers |
| `codeFormatter` / `codeFormatters` | One or all code formatters |
| `installation` | Details about the DeepSource installation |
| `node(id)` | Global object lookup by relay ID |

### Nested under `repository`

`analysisRuns`, `pullRequest(number)`, `pullRequests`, `issues`, `issueOccurrences`,
`ignoreRules`, `reports`, `metrics`, `enabledAnalyzers`, `targets`,
`dependencyVulnerabilityOccurrences`.

### Nested under `account`

`repositories`, `members`, `reports`, `suppressedIssues`.

---

## Mutation categories

| Category | Examples |
|----------|----------|
| Repository management | `activateRepository`, deactivate analysis, regenerate DSN, `updateRepositoryDefaultBranch` |
| Quality gates | `updateRepositoryIssueCategorySetting`, configure priorities and metric thresholds |
| Issue suppression | suppress / unsuppress issues across repositories at the team level |

---

## Query examples

### Authenticated user

```graphql
query {
  viewer {
    email
  }
}
```

### Fetch a repository

```graphql
query {
  repository(name: "demo-go", login: "cyberdyne", vcsProvider: GITHUB) {
    name
    defaultBranch
    dsn
    isPrivate
    isActivated
  }
}
```

### Analysis runs and issues for a repository

```graphql
query {
  repository(name: "my-app", login: "myorg", vcsProvider: GITHUB) {
    analysisRuns {
      edges {
        node {
          runUid
        }
      }
    }
    issues {
      edges {
        node {
          issue {
            shortcode
          }
        }
      }
    }
  }
}
```

### Dependency vulnerabilities (SCA)

```graphql
query {
  repository(name: "my-app", login: "myorg", vcsProvider: GITHUB) {
    dependencyVulnerabilityOccurrences(first: 10) {
      edges {
        node {
          vulnerability {
            identifier
            severity
            cvssV3BaseScore
          }
          package {
            name
            ecosystem
          }
        }
      }
    }
  }
}
```

### List analyzers

```graphql
query {
  analyzers {
    edges {
      node {
        name
        shortcode
      }
    }
  }
}
```

---

## Mutation examples

### Activate analysis on a repository

```graphql
mutation ($input: ActivateRepositoryInput!) {
  activateRepository(input: $input) {
    ok
  }
}
```

### Update the default (baseline) branch

```graphql
mutation ($input: UpdateRepositoryDefaultBranchInput!) {
  updateRepositoryDefaultBranch(input: $input) {
    ok
    repository {
      defaultBranchName
    }
  }
}
```

### Configure an issue-category quality gate

```graphql
mutation ($input: UpdateRepositoryIssueCategorySettingInput!) {
  updateRepositoryIssueCategorySetting(input: $input) {
    ok
  }
}
```
