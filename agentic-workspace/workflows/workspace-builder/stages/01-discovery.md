# Stage 01: Discovery

Understand the domain workflow through structured conversation with the owner. The
stage produces a workflow map, not a scaffold and not a final policy decision.

## Inputs

| Source | Scope | Why |
|---|---|---|
| Run request | Full request and setup answers | Establish the domain and desired outcome |
| Owner or authorized actor | Conversation and supplied material | Describe the real workflow, constraints, and decisions |
| `references/conventions-reference.md` | Full file | Discover toward ADS workspace and workflow contracts |
| `references/example-workspace-profile.md` | Full file | Provide a concrete comparison point |

## Process

1. Ask the owner to describe the workflow from its first input to its final accepted result.
2. Identify distinct responsibilities and natural handoff or review points.
3. For every proposed stage, record inputs, process responsibility, output artifact, required context, actor, authority, completion, and failure behavior.
4. Identify shared context and keep it separate from stage-specific references.
5. Identify installation or run-specific values and name them as variables.
6. Identify optional stages, branching, retry, stop, and escalation conditions.
7. Identify tool prerequisites, required Capabilities, likely implementations, and any public interface needs.
8. Present the draft map and ask whether stages, handoffs, inputs, outputs, or authority boundaries are missing or incorrectly split.
9. Apply the audit below, revise failures, and write the workflow map to the run artifact location.

## Checkpoint

| Agent presents | Owner decides |
|---|---|
| Draft stage map with inputs, outputs, shared context, variables, optional paths, tools, Capabilities, and handoffs | Whether the workflow shape and boundaries describe the intended work |

## Audit

| Check | Pass condition |
|---|---|
| Stage clarity | Every stage has one primary responsibility and a named output |
| Input/output chain | Every input is supplied by the request, a declared source, or a prior stage |
| Shared context | Cross-stage sources are listed separately from stage-local references |
| Variable coverage | Every installation- or run-specific value has a named variable or recorded decision |
| Authority coverage | Each consequential action, review, acceptance, and promotion point has an owner |
| Failure coverage | Missing input, denial, ambiguity, retry, and escalation behavior are named where relevant |

## Output

Write `runs/<run-id>/artifacts/01-discovery/workflow-map.md` containing the stage map,
shared context, variables, optional paths, prerequisites, Capability needs, authority
and interface notes, checkpoint decision, and audit evidence.
