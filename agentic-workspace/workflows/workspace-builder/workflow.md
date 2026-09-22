# Workspace Builder Workflow

**ID:** `workspace-builder`
**Version:** `0.1`
**Status:** Proposed

Build a new filesystem-backed or service-backed workspace for a coherent domain of
work. The workflow moves from domain discovery to inspectable stage contracts, a
candidate workspace scaffold, onboarding design, and validation.

This is a workflow within a workspace. It does not create authority, publish a
workspace, or replace the workspace kernel. Its final scaffold is a working artifact
until the declared acceptance measures pass and an authorized owner promotes it.

## Entry contract

| Field | Contract |
|---|---|
| Request | A request to create or materially reshape one workspace for a named domain |
| Required input | Domain purpose, intended users or actors, desired outcome, and any known workflow description |
| Optional input | Existing policies, examples, templates, tools, source systems, interface requirements, and target location |
| Allowed actors | Human owner, authorized agent, or mixed team acting within the run authority |
| Initial context | This workflow definition, `setup/questionnaire.md`, and the references listed below |
| Candidate output | A complete workspace scaffold, setup questionnaire, contracts, and validation report |
| Promotion authority | The workspace owner or explicitly delegated authority; never the builder run by itself |

Use the setup questionnaire when the request does not provide enough information to
start discovery. The questionnaire is an intake aid, not a substitute for the
discovery checkpoint.

## Entry routes

| Route | Behavior |
|---|---|
| `setup` | Create a run, ask or load the setup questionnaire, pin the request and context, then route to stage 01 |
| `status` | Read the run record and transition history and report each stage as pending, active, blocked, complete, or awaiting acceptance |

`status` reads the run record as the source of truth. It must not infer completion
merely from the presence of files in an artifact folder.

## Required Capabilities

The workspace resolves these Capabilities before a run starts. The binding may be a
human, agent, script, service, or mixed implementation.

| Capability | Use in this workflow |
|---|---|
| Context Provider | Retrieve the ADS model, supplied references, examples, and declared source material |
| Context Assembly | Assemble the request-scoped domain, authority, tool, and convention context |
| Interaction | Ask setup questions, present checkpoints, receive corrections, and record decisions |
| Work | Draft contracts, produce the candidate scaffold, and apply in-run corrections |
| Storage | Persist the request, pinned context, stage artifacts, evidence, decisions, and status |
| Evaluation | Run the stage audits and final validation against the acceptance snapshot |

Bindings must record the Capability contract version, implementation identity and
version when available, configuration, authority context, and result provenance.

## References

Load only the references required by the active stage:

- `setup/questionnaire.md` -- intake questions for starting a builder run.
- `references/conventions-reference.md` -- ADS rules and source-workflow translation notes.
- `references/placeholder-syntax.md` -- syntax used in generated workspace templates.
- `references/example-workspace-profile.md` -- a compact completed profile for comparison.

Each stage definition identifies its own inputs. Do not load later stages merely to
complete an earlier stage.

## Stages

| Stage | Purpose | Primary output | Transition |
|---|---|---|---|
| 01 Discovery | Understand the domain workflow and its boundaries | `runs/<run-id>/artifacts/01-discovery/workflow-map.md` | Human checkpoint, then continue or revise |
| 02 Mapping | Formalize stage contracts and the dependency graph | `runs/<run-id>/artifacts/02-mapping/stage-contracts.md` | Human checkpoint, then continue or return to discovery |
| 03 Scaffolding | Generate the complete candidate workspace structure and files | `runs/<run-id>/artifacts/03-scaffolding/workspace-scaffold/` | Audit, then continue or return to mapping |
| 04 Questionnaire Design | Derive onboarding questions and placeholder coverage | `runs/<run-id>/artifacts/04-questionnaire-design/questionnaire.md` | Human checkpoint, then continue or revise scaffold/discovery |
| 05 Validation | Verify conventions, references, coverage, and handoffs | `runs/<run-id>/artifacts/05-validation/validation-report.md` | Pass to acceptance or return to the implicated stage |

Stages are reusable definitions. The paths above are run-artifact locations, not
folders inside this workflow definition.

## Run record and isolation

Before stage 01 begins, create and pin a run record containing:

- the request and setup answers;
- the resolved-context manifest and Capability bindings;
- this workflow version and the acceptance snapshot;
- the actor and authority context;
- transition history and checkpoint decisions; and
- the target workspace location, if one was supplied.

The run keeps its artifacts and evidence under an isolated location such as:

```text
runs/<run-id>/
├── run.md
├── request.md
├── resolved-context.yaml
├── acceptance-snapshot.md
├── transitions.md
├── artifacts/
│   ├── 01-discovery/workflow-map.md
│   ├── 02-mapping/stage-contracts.md
│   ├── 03-scaffolding/workspace-scaffold/
│   ├── 04-questionnaire-design/questionnaire.md
│   └── 05-validation/validation-report.md
└── evidence/
```

The candidate scaffold may be copied to a target workspace only during promotion.
No stage writes directly to an authoritative workspace location.

## Acceptance measures

The result is acceptable only when the final validation report records a pass, or an
explicitly accepted non-blocking exception, for every measure below:

1. The workspace has one clear purpose, owner, maintenance path, boundary, and target audience.
2. Every generated workflow stage has a complete Inputs, Process, Outputs, and completion contract.
3. The stage and workspace reference graph is directed and has no unresolved circular dependency.
4. Each durable fact, rule, and decision has one authoritative home; other files reference it.
5. User-specific values and optional branches have complete placeholder and questionnaire coverage.
6. The candidate declares context sources, authority boundaries, required Capabilities, bindings, workflows, interfaces, run isolation, acceptance, promotion, and maintenance.
7. Cross-references resolve within the candidate workspace or to an explicitly declared public interface or published source.
8. Candidate files contain working definitions only; request-specific outputs remain in the run.
9. Required checkpoint decisions, audit evidence, and validation findings are recorded.

An unresolved authority, isolation, broken-reference, or acceptance defect is blocking
and must stop promotion.

## Transition policy

| Evaluation | Action |
|---|---|
| Stage output complete and checkpoint accepted | Continue to the next stage |
| Missing or ambiguous domain information | Stop and ask the owner; preserve the run |
| Stage audit fails | Revise the current stage artifact and rerun its audit |
| Mapping reveals a missing or incorrectly split stage | Return to stage 01 |
| Scaffold cannot satisfy a mapped contract | Return to stage 02; do not silently weaken the contract |
| Questionnaire coverage fails | Return to stage 01, 03, or 04 as identified by the finding |
| Validation is inconclusive or evidence is stale | Stop or retry according to the run record; never treat it as acceptance |
| Validation passes | Mark workflow complete, then request acceptance |
| Acceptance granted | Promote the candidate to its authoritative destination |
| Acceptance denied or withdrawn | Keep the candidate and evidence in the run; do not promote |

Completion, acceptance, and promotion are separate events. Promotion must record the
accepted artifact identity, validation evidence, authority, destination, and any
follow-up maintenance work.

## Non-goals

This workflow does not decide the domain's business policy, invent missing authority,
implement domain tools, migrate an existing production workspace, or expose another
workspace's private files. Those concerns require explicit inputs, interfaces, or a
separate workflow.
