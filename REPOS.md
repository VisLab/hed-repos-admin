# HED repository map

One row per repository. Two groups, distinguished by where the main source lives and how updates flow:

1. **General-purpose HED repositories** - main source in the GitHub `hed-standard` organization, used by the HED community. Updated by pull request from a branch in another repository (for Kay, a fork under `VisLab`) - never by direct push.
2. **Research repositories** - ongoing research, not community deliverables. Hosted under `VisLab` and updated by pushing directly to the repo, no PR; some are local only and not pushed at all (see the Hosting column).

Rows marked "(review)" are inferred, not confirmed. Repositories are referred to by name, never by path.

## General-purpose HED repositories (hed-standard)

All of these repositories are interdependent in that one repository depends on information from another.

| Category | Repo | Purpose |
| --- | --- | --- |
| tools | `hed-python` | The `hedtools` package: schema loading, validation, BIDS handling, analysis |
| tools | `hed-javascript` | HED tools in JavaScript, including the validator used by the BIDS validator (review) |
| tools | `hed-typescript` | HED tools in TypeScript (review) |
| tools | `table-remodeler` | Restructuring and remodeling of tabular event files (review) |
| tools | `hed-matlab` | HED tools for MATLAB |
| tools | `hed-vis` | Visualization library for HED-annotated data (`hedvis` on PyPI): word clouds and visual summaries; will hold the task-model generator code |
| tools | `hed-mcp` | MCP server exposing HED tools to AI assistants |
| tools | `ndx-hed` | NWB extension that adds HED annotations to any NWB `DynamicTable` (`ndx-hed` on PyPI) |
| spec | `hed-specification` | The formal HED specification and annotation rules |
| vocabulary | `hed-schemas` | The HED vocabularies: schema source of truth |
| data | `hed-examples` | Curated example BIDS datasets and use cases |
| data | `hed-tests` | Test data for hed validators |
| docs | `hed-resources` | User-facing documentation and resources |
| docs | `hed-task` | Documentation about tasks; distinct from the local-only task-research working area |
| servers | `hed-server` | Deployable HED server with UI and REST |
| servers | `hed-web` | The browser-based HED tools |

## Research repositories (VisLab)

Updated by direct push; no PR workflow.

### Coordination

| Repo | Purpose | Depends on |
| --- | --- | --- |
| `hed-repos-admin` | This repo: the map and cross-repo coordination while the repos are standardized | nothing |
| `claude-advice` | General AI-assistant advice for any repo: repo standards, `.status/` conventions, templates, the triage script | nothing |

### Task/metadata cluster

| Repo | Purpose | Depends on | Hosting |
| --- | --- | --- | --- |
| `hed-task-models` | Graph models of tasks: the model spec (`model_rules.md`) and worked examples; data, no code | `hed-vis` for code, `hed-examples` for source datasets | VisLab |
| `hed-metadata-toolkit` | Metadata tooling; the finished reference example of the standardized repo layout |  | VisLab |
| `nemar-metadata` | NEMAR dataset metadata: curated summary files  | `hed-metadata-toolkit` | local only; has a VisLab remote but is not pushed |
| `task-research` | Task-research working material |  | local only; no remote, never pushed |

### EEG preprocessing

| Repo | Purpose | Depends on | Hosting |
| --- | --- | --- | --- |
| `EEG-Clean-Tools` | The PREP pipeline: standardized early-stage EEG preprocessing (line-noise removal, robust referencing, bad-channel detection and interpolation, reporting) as a MATLAB toolbox and EEGLAB plugin | EEGLAB (external) | VisLab |

