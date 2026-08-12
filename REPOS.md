# HED repository map

**DRAFT - rows marked "(review)" are inferred, not confirmed.** One row per repository, grouped by cluster. A cluster is a set of repos that genuinely share plans and data flows; cross-repo material for one cluster lives with that cluster, and only genuinely cross-cluster material lives in this repo.

Repositories are referred to by name, never by path.

## Coordination

| Repo | Purpose | Owns | Depends on |
| --- | --- | --- | --- |
| `hed-repos-admin` | This repo: the map and cross-repo coordination while the repos are standardized | `REPOS.md` | nothing |
| claude-advice | General AI-assistant advice for any repo: repo standards, `.status/` conventions, templates, the triage script | the checklists and templates the standardization applies | nothing (review: org/visibility) |

## Core HED (hed-standard)

| Repo | Purpose | Owns | Depends on |
| --- | --- | --- | --- |
| `hed-python` | The `hedtools` package: schema loading, validation, BIDS handling, analysis | all core HED functionality | `hed-schemas` |
| `hed-schemas` | The HED vocabularies | schema source of truth | nothing |
| `hed-specification` | The formal HED annotation rules | the spec | nothing |
| `hed-examples` | Curated example BIDS datasets and use cases | test and demonstration data | `hed-schemas` |
| `hed-resources` | Documentation and resources (review) | user-facing docs (review) | (review) |

## Visualization (VisLab)

| Repo | Purpose | Owns | Depends on |
| --- | --- | --- | --- |
| `hed-vis` | Visualization library for HED-annotated data (`hedvis` on PyPI): word clouds and visual summaries | visualization code; will hold the task-model generator code | `hed-python` (`hedtools`) |
| `hed-task-models` | Graph models of tasks: the model spec (`model_rules.md`) and worked examples; data, no code | the canonical spec and models | `hed-vis` for code, `hed-examples` for source datasets |

## Metadata (review: cluster name and membership)

| Repo | Purpose | Owns | Depends on |
| --- | --- | --- | --- |
| `hed-metadata-toolkit` | Metadata tooling; the finished reference example of the standardized repo layout | the layout every repo is standardized to | (review) |
| nemar-metadata | NEMAR dataset metadata (review) | curated summary files, `datasets/` (review) | `hed-metadata-toolkit` |

## Task research (task-research's own cluster)

| Repo | Purpose | Owns | Depends on |
| --- | --- | --- | --- |
| task-research | The task-research cluster's home: its cross-cutting thinking and, after standardization, its cluster map and skills | task-research working material | (review) |
| `hed-task` | (review: purpose, and whether it is distinct from task-research) | (review) | (review) |

## To classify

Repositories Kay has worked with that are not yet placed in a cluster; classify or strike as each is standardized: `ctagger`, `hed-agents`, `hed-bot`, `hed-curation`, `hed-data`, `hed-javascript`, `hed-matlab`, `hed-mcp`, `hed-ontology`, `hed-schema-browser`, `hed-server`, `hed-standard.github.io`, `hed-tests`, `hed-typescript`, `hed-web`. Upstream checkouts that are not Kay's to standardize (review): `bids-examples`, `bids-specification`, `bids-validator`.

Abandoned, do not revive: `openneuro-metadata` (its design docs were rescued into `hed-metadata-toolkit`).
