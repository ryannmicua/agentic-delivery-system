# Stage 03: Scaffolding

Generate a complete candidate workspace from the mapped contracts. The candidate is a
run artifact and remains non-authoritative until acceptance and promotion.

## Inputs

| Source | Scope | Why |
|---|---|---|
| `artifacts/02-mapping/stage-contracts.md` | Full file | Define the stage and workflow contracts to realize |
| `references/conventions-reference.md` | Full file | Apply ADS workspace and boundary rules |
| `references/placeholder-syntax.md` | Full file | Generate inspectable variables and conditional sections |
| Resolved context manifest | Declared templates, policies, tools, and interfaces | Preserve supplied domain constraints |

## Process

1. Translate the mapped contracts into a candidate workspace inventory before writing files.
2. Create the workspace entry point with purpose, ownership, scope, routes, authority, Capabilities, interfaces, working-state locations, acceptance, promotion, and maintenance.
3. Create logical roots for context, capabilities, bindings, workflows, interfaces, runs, accepted artifacts, evaluations, and maintenance as needed by the mapped design.
4. Generate workflow and stage definitions with references to canonical sources rather than copied policy.
5. Add setup guides or prerequisite records for every required tool, and mark optional tools and conditional stages.
6. Add the generated workspace's setup questionnaire placeholders and a manifest of the intended bindings.
7. Keep run records, artifacts, and evidence out of reusable definition folders; empty run roots may contain only explicit placeholders such as `.gitkeep`.
8. Record the candidate file inventory and any unresolved implementation choices.
9. Apply the audit below before handing the candidate to questionnaire design.

## Candidate minimum shape

The physical tree is configurable, but the candidate must provide homes for the
concepts it declares. A typical filesystem binding is:

```text
<candidate-workspace>/
├── README.md
├── context/
├── capabilities/
├── bindings/
├── workflows/
├── interfaces/
├── runs/
├── accepted/
├── evaluations/
└── maintenance/
```

## Audit

| Check | Pass condition |
|---|---|
| Kernel completeness | Purpose, boundary, owner, context, authority, Capabilities, workflows, interfaces, state, acceptance, promotion, and maintenance are declared |
| Contract realization | Every mapped stage and transition has a corresponding candidate definition |
| Reference integrity | Candidate references resolve to candidate files, declared public interfaces, or published sources |
| Authority separation | Tools, bindings, and files do not imply permission, acceptance, or promotion |
| Run isolation | Candidate definitions do not contain request-specific outputs or status |
| Naming and placeholders | Names are portable and placeholders follow `placeholder-syntax.md` |
| Inventory evidence | Every generated file has a purpose and an owner |

## Output

Write the candidate tree under
`runs/<run-id>/artifacts/03-scaffolding/workspace-scaffold/`. Also write a scaffold
inventory and audit record in the same stage artifact directory. Do not write to the
target workspace during this stage.
