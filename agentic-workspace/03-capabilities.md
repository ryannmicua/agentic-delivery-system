# Capabilities

## Definition

A **Capability** is a stable contract for a bounded workspace function. It defines
what the workspace can rely on, not how the function is realized.

A workspace selects the Capabilities required by its workflows. A
**Capability Implementation** is the local or external realization of a Capability.
It may be a human, AI agent, script, service, tool, or combination of these.

A workflow is a separate concept: it defines a reusable path for producing an outcome.
A workflow may implement a Capability when it is explicitly bound and conforms to that
Capability's contract, and it may require other Capabilities to perform its stages.
This is optional; a workflow does not need a formal Capability, and workflows are not
the only possible Capability Implementations.

Teams may use informal terms such as *component*, *action*, *process*, or *handler*
for a Capability Implementation. Those terms are local language only. Contracts,
bindings, and run records use the formal term **Capability Implementation**.

## Minimum Capabilities

The minimum Capability set contains six bounded functions. The recommended shorthand
is:

> Context provides. Context Assembly selects. Work acts. Storage persists. Evaluation
> assesses. Interaction exchanges.

These are Capabilities, not workflow stages. A workspace need not use all six, and no
Capability implies a required execution order.

### Shared contract

Every Capability declares:

- Capability name and contract version;
- purpose and scope;
- inputs, outputs, and required context;
- required authority and permissions;
- side effects and failure behavior;
- provenance; and
- owner, maintenance path, and conformance checks.

Operational details such as caching, retries, concurrency, durability, cancellation,
and resource limits belong in the Capability Implementation profile. An
implementation profile declares these details when they are relevant to the
Capability or its risk; they are not implied by the Capability alone.

### Context Provider

Context Provider retrieves or exposes source-backed information for a declared source,
query, and scope.

Its contract declares:

- source identity, authority, version, freshness, and access limits;
- the query and scope it accepts;
- returned items or references;
- provenance and integrity information; and
- behavior for missing, stale, partial, or denied results.

Boundary: Context Provider provides source material. It does not determine the complete
context for a task.

### Context Assembly

Context Assembly creates a task-scoped context package from available sources.

Its contract declares:

- the task or context request and selection constraints;
- inclusion, exclusion, ranking, and precedence rules;
- conflict handling;
- what was included, excluded, and prioritized;
- unresolved gaps and freshness; and
- reproducible provenance explaining the assembly.

Boundary: Context Assembly selects and combines relevant material for a task. It does
not replace authoritative sources or grant authority.

Context Provider and Context Assembly should remain separate when multiple sources,
conflicts, freshness, privacy or authority filtering, or task-specific relevance make
the distinction useful. In a simple workspace, one Capability Implementation may
provide both internally. Neither is a mandatory workflow stage.

### Work

Work performs a bounded operation requested by a workflow or authorized actor.

Its contract declares:

- the operation, parameters, and preconditions;
- required context, authority, and permissions;
- outputs, changes, artifacts, and records;
- external effects and their reversibility;
- retry, cancellation, timeout, and recovery behavior;
- execution status; and
- executor and action provenance.

Boundary: Work performs the authorized action. It does not expand authority or
implicitly accept or promote results.

### Storage

Storage persists and retrieves run state, records, artifacts, and evidence.

Its contract declares:

- supported operations and addressing;
- identity, version, and integrity behavior;
- durability, consistency, and concurrency guarantees;
- retention, deletion, and recovery behavior;
- access and isolation boundaries;
- conflict and partial-write behavior; and
- retrieval provenance.

Boundary: Storage makes material durable or available. Storage alone does not make
material authoritative, accepted, or promoted.

### Evaluation

Evaluation assesses a claim, result, artifact, or change against declared criteria and
evidence.

Its contract declares:

- the subject and criteria, including criteria version;
- evidence required and evidence used;
- method and evaluator;
- findings, contradictions, gaps, and uncertainty;
- outcome, such as pass, fail, inconclusive, or advisory; and
- reproducibility and review data.

Boundary: Evaluation produces an assessment. It does not itself constitute acceptance
or promotion authority.

### Interaction

Interaction exchanges information, requests, feedback, and control signals with a
human, agent, or external system.

Its contract declares:

- participants, identities, roles, and channel;
- message or request format;
- correlation, session, and delivery semantics;
- acknowledgement, timeout, retry, and duplicate behavior;
- confidentiality, authentication, and retention;
- escalation and handoff behavior; and
- response or transcript provenance.

Boundary: Interaction enables and records communication. It does not grant authority
or turn an unverified request into approval.

## Capability, Implementation, Binding, and Configuration

| Item | Role |
|---|---|
| Capability | The stable contract for a bounded workspace function. |
| Capability Implementation | A concrete local or external realization of a Capability. |
| Binding | Connects a workspace Capability requirement to a selected Capability Implementation and records the relevant contract and implementation versions. |
| Configuration | Applies workspace-specific settings without redefining the Capability. |

If one Capability Implementation provides multiple Capabilities, each Capability
remains separately identifiable by its contract, boundary, permissions, effects, and
result. A workflow that composes several Capabilities is still a workflow, not a new
Capability by default. It becomes a Capability Implementation only when an explicit
binding declares that it implements a particular Capability contract.

The binding and each consequential run record, at minimum, the Capability name and
contract version, Capability Implementation identity and version when available,
configuration, authority context, and result provenance.

## What Is Not a Capability

The following are not Capabilities by default:

- a workflow that has not been explicitly bound as a Capability Implementation, a run,
  artifact, record, decision, or work item;
- evidence, acceptance, or promotion state;
- an authority rule or configuration value; or
- an arbitrary file, prompt, or tool without a defined Capability contract.

A Capability Implementation may remain local to a workspace. It does not need to be
generalized, published, or reused to satisfy a Capability requirement.

## Capability Conformance and Change

A workspace verifies that each Capability Implementation is available, correctly bound,
authorized, and producing results that satisfy the Capability contract. A broad local
label such as "agent," "tool," or "integration" is not sufficient evidence of
conformance.

Changes to a Capability contract and changes to a Capability Implementation are
tracked separately. A material contract change requires a new contract version or an
explicit compatibility decision. A material implementation change records its effect
on active bindings and runs.
