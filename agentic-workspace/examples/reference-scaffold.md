# Reference Scaffold

This is a deliberately small filesystem-backed example. It shows a workspace with two
workflow routes and one isolated sample run. Names and paths are illustrative bindings,
not requirements of the conceptual model.

```text
content-workspace/
├── README.md                         # workspace entry point and route list
├── context/
│   ├── shared-policy.md              # workspace context
│   └── source-index.md
├── workflows/
│   ├── draft-delivery/               # route 1: an ICM-style pipeline -> workflow
│   │   ├── workflow.md               # entry contract, acceptance, transitions
│   │   ├── references/
│   │   │   └── editorial-guide.md
│   │   └── stages/                    # reusable definitions only
│   │       ├── 01-assemble-context.md
│   │       ├── 02-draft.md
│   │       └── 03-evaluate.md
│   └── answer-review/                # route 2: a shorter workflow
│       └── workflow.md
├── runs/
│   └── run-2026-09-22-001/           # isolated request-specific location
│       ├── run.md                    # human-readable record and current status
│       ├── request.md
│       ├── resolved-context.yaml
│       ├── acceptance-snapshot.md    # pinned before execution
│       ├── transitions.md
│       ├── artifacts/
│       │   ├── 01-assemble-context/
│       │   ├── 02-draft/
│       │   └── 03-evaluate/
│       └── evidence/
└── accepted/                         # authoritative results after promotion
```

The `draft-delivery` workflow can declare, for example:

```yaml
id: draft-delivery
version: 1.0
entry:
  request: content brief
  required_context: [shared-policy, source-index]
stages:
  - id: 01-assemble-context
    input: content brief
    output: resolved context package
    completion: sources and gaps are recorded
  - id: 02-draft
    input: resolved context package
    output: draft artifact
    completion: draft follows editorial guide
  - id: 03-evaluate
    input: draft artifact
    output: evaluation and evidence
    completion: every acceptance measure has a result
acceptance:
  - all required claims have source evidence
  - editorial guide checks pass
  - no unresolved critical gaps
transitions:
  pass: complete
  fail: stop-and-escalate
  inconclusive: return-to-draft
```

The sample run copies the resolved values into its own manifest and acceptance
snapshot. Later edits to the workflow, references, or workspace bindings apply to new
runs, not silently to this run. Completion of the run does not itself accept or promote
the draft.
