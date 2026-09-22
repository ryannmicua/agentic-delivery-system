# Workflows and Runs

## Workflow definition

An **Agentic Workflow** is a reusable, inspectable definition for a route through
work. It belongs to an Agentic Workspace; the workspace is the environment and may
contain one or more workflows. A canonical ICM pipeline maps to one workflow, not to
the whole workspace.

A workflow is not identical to a Capability. It describes an ordered path, while a
Capability describes a bounded function. A workflow may implement a Capability when
an explicit binding says so, and it may require other Capabilities. It may also simply
be a local route with no formal Capability of its own.

Every reusable workflow has a small contract:

- **Entry contract:** request shape, required inputs, allowed route/actor, authority
  boundary, and the initial context needed to start.
- **Numbered stages:** human-navigable stages with a purpose, inputs, outputs, and
  stage-specific completion checks. Stage definitions are reusable; they are not run
  storage.
- **References:** workflow-specific instructions, examples, source lists, templates,
  or policies, resolved through the workspace's context rules.
- **Acceptance:** testable measures and required evidence defined before execution.
- **Transition policy:** the evaluated conditions for continuing, stopping, escalating,
  retrying, or returning to an earlier stage. Human review may be one condition, but is
  not mandatory when automatic evaluation is sufficient.
- **Required Capabilities:** optional declarations of Capabilities used by the route,
  with bindings resolved by the workspace.

The workflow contract should be readable without opening a runtime. A route selects a
workflow and supplies a request; it does not modify the workflow definition while a
run is active.

## Run definition

A **Run** is one execution of one workflow for one request. Every run gets an explicit
run ID and an isolated run location. Before execution starts, the run records or pins:

- the request and entry inputs;
- the resolved-context manifest, including relevant definition, reference, binding,
  and implementation versions;
- the workflow version and transition policy;
- the acceptance measures and required evidence snapshot; and
- the authority and actor context needed for the execution.

The isolated location also contains a human-readable run record/status, artifacts
organized by stage, evidence, failures, and transition history. Output belongs to the
run even when it is produced while a stage is active. A workflow's `stages/` folder
contains reusable definitions only; it is never an output or status store.

Completion, acceptance, and promotion remain separate:

1. **Completion** says the workflow reached its declared end or stop condition.
2. **Acceptance** says evaluation found that the pinned measures were met, subject to
   any declared human review or approval requirement.
3. **Promotion** moves an accepted result to its authoritative destination.

Automatic continuation is allowed only when evaluation has produced the result required
by the transition policy. A failed, inconclusive, missing, or stale evaluation must
stop, retry, or escalate according to that policy; it must not be treated as implicit
acceptance.

## ICM-to-ADS mapping

| ICM concept | Agentic Delivery System concept |
|---|---|
| Pipeline | Agentic Workflow route within an Agentic Workspace |
| Stage | Numbered workflow stage with a stage contract |
| Shared references | Workspace context or workflow-specific references |
| Output | Run artifact stored under the isolated run location |
| Checkpoint | Evaluated transition policy: continue, stop, retry, return, or escalate |
| Status | Human-readable run record/status, optionally exposed through a workspace interface |

The mapping preserves ICM's useful human navigation while avoiding a claim that a
directory tree is the architecture. The reference scaffold uses filesystem paths as
one implementation; another implementation may use a database, service, or other
storage while preserving the same contracts and isolation.
