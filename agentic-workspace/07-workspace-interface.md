# Workspace Interface

## Definition

A **Workspace Interface** is a versioned public contract owned by a provider
workspace. It defines the interaction that another workspace, human, agent, or
external system may have with the provider without receiving access to the
provider's private context, files, bindings, drafts, or run state.

An interface is a boundary contract, not a transport. It may be realized by a
local adapter, file exchange, service, message channel, or another mechanism.
The realization may change while the published contract remains compatible.

The provider publishes the interface. A consumer uses an **Interface Binding** to
select the provider interface version and the operations it is allowed to invoke.
The binding is workspace configuration; it does not copy the provider's
definitions or grant access to its storage.

## What an Interface Contract Declares

Every published interface declares enough information for a consumer to decide
whether and how to use it:

- **identity and version** — stable interface identity, provider workspace, contract
  version, lifecycle status, and compatibility or deprecation information;
- **ownership** — the workspace and maintenance owner responsible for the contract,
  its implementation, and its published behavior;
- **audience** — allowed consumer workspaces or consumer classes, including any
  parent, child, sibling, human, agent, or external-system relationship;
- **operations** — operation identity, purpose, whether it is read-only or a
  command, and whether it is synchronous or may remain in progress;
- **inputs and outputs** — required fields, references, constraints, output shapes,
  provenance, and whether an output is a result, evidence summary, accepted
  artifact, or explicit handoff;
- **status** — the public lifecycle states and the information visible in each
  state;
- **failures** — stable failure categories, whether a failure is retryable, what
  may have changed, and what action or authority is required next;
- **retry and idempotency** — duplicate-request behavior, idempotency-key rules,
  retry limits or responsibilities, and cancellation behavior when relevant;
- **side effects** — systems or records read or changed, publication and promotion
  effects, reversibility, and the point at which an external effect is committed;
- **authority** — provider-side authority required to perform each operation,
  consumer authority required to request it, and decisions the interface does not
  delegate; and
- **privacy** — information published, information withheld by default, and any
  separately governed operation that can expose more detail.

The interface contract should also identify the provenance retained for each
operation: request identity, provider and interface version, relevant workflow or
Capability versions, actor or executor, evidence references, and publication or
acceptance decisions. It need not expose all of that provenance to the consumer;
the contract states which summary is public.

## Public Operation Semantics

An operation is the smallest externally invocable unit in an interface. An
operation may delegate to one or more provider workflows and Capabilities, but the
consumer depends only on the operation contract.

### Request

Each invocation carries, at minimum:

- the interface identity and contract version selected by the consumer;
- operation identity;
- consumer identity and authority context;
- a consumer-generated correlation or request identifier;
- an idempotency key for any operation that can create or change state; and
- the operation input, including references to published context or accepted
  artifacts rather than paths into the provider's private storage.

The provider validates the interface version, audience, operation, input, and
authority before doing work. An interface does not turn an untrusted request into
approval, acceptance, promotion, or a new authority grant.

### Status

An interface may expose a public status projection such as:

```text
acknowledged -> in_progress -> completed
                          \-> failed
```

`rejected` and `cancelled` may be used when the provider declines the request or
stops it before completion. A completed operation may separately report whether a
result was accepted or whether promotion occurred; `completed` must not be
interpreted as `accepted` or `promoted`.

The public projection may include an invocation identifier, timestamps, a safe
summary, progress milestones, an expected next update, and links or references to
published outputs. It does not expose private run state by default. Private logs,
intermediate context, raw tool calls, internal decisions, and working artifacts
remain provider-owned unless a separate governed operation explicitly publishes a
summary or artifact.

### Result

A successful result identifies what was produced and its trust state. It should
make the following distinctions explicit:

- a working result is not an accepted artifact;
- an evidence summary describes evidence but is not itself acceptance;
- an accepted artifact is available at a declared authoritative or handoff
  destination; and
- a handoff records what the receiving party is expected to do next and who retains
  responsibility.

The interface may return a result immediately or return an acknowledged,
in-progress invocation that the consumer later observes through a declared status
operation or callback-like implementation. The contract does not require a
particular transport.

### Failure

A failure is a public contract result, not an instruction to inspect private run
state. A failure should include:

- a stable category or code;
- whether the request was rejected before work, failed during work, or completed
  with a partial result;
- whether retrying with the same or a new idempotency key is safe;
- any known committed or published side effect;
- the safe explanation visible to the consumer; and
- the next required action, escalation, or authority.

Failure details must not disclose secrets or private provider material merely to
make diagnosis easier. The provider may retain richer diagnostics privately and
publish an evidence or failure summary instead.

## Retry, Idempotency, and Side Effects

The operation contract declares whether it is read-only, creates provider state,
changes an existing artifact, publishes an accepted artifact, promotes a result,
or produces an external effect. It also declares whether that effect is reversible,
retry-safe, or compensatable.

For a state-changing operation, the provider treats a repeated idempotency key as
the same logical request for the retention period declared by the interface. A
duplicate request must return the original acknowledgement, current public status,
or terminal result rather than silently creating a second effect. If the provider
cannot provide that guarantee, the operation must say so and the consumer must not
retry it automatically.

Timeout is not proof that no effect occurred. After an uncertain timeout, the
consumer uses the original correlation or idempotency key with the declared status
operation before deciding whether to retry. The provider reports partial effects
and recovery or compensation requirements when an operation fails after an effect.

Read-only operations may still require authority and may still disclose sensitive
information. Read-only does not mean public.

## Authority at the Boundary

Authority remains with the workspace that owns the relevant resource or decision.
The interface declares the boundary conditions, but it is not a full RBAC or ABAC
system. At minimum, the provider identifies:

- the provider owner and resources or decisions it controls;
- the consumer identities or relationships allowed to invoke each operation;
- the provider-side authority required before the operation can run;
- any consumer-side authority or approval that must accompany the request; and
- decisions the provider will never infer or delegate through that operation.

An interface may accept a request to evaluate, prepare, or propose a change without
accepting authority to approve, promote, or publish it. Any delegated authority is
explicitly scoped to the operation and its declared effects.

## Consumer Interface Binding

A consumer binds to a provider interface by recording, at minimum:

- provider workspace identity;
- interface identity and the exact contract version or compatible version range;
- the provider's published interface reference or adapter configuration;
- the operations the consumer intends to use;
- the consumer identity and authority context used for those operations;
- the expected input and output contract versions;
- the consumer's retry, timeout, and duplicate-handling policy, subject to the
  provider's contract; and
- binding status, owner, and review or expiry information when relevant.

The binding must not contain a path to the provider's private root as a substitute
for the interface reference. It must not silently widen the audience or operations
declared by the provider.

Invocation proceeds conceptually as follows:

1. The consumer resolves its Interface Binding and selects a published contract
   version.
2. The consumer validates the operation input and adds correlation and idempotency
   identifiers as required.
3. The provider checks the interface version, audience, authority, and side-effect
   preconditions.
4. The provider acknowledges, rejects, or begins the operation and exposes only the
   declared public status projection.
5. The consumer receives the declared result, failure, evidence summary, accepted
   artifact, or explicit handoff.
6. Both workspaces retain provenance appropriate to their own runs; neither gains
   direct access to the other's private run state.

## Relationship to Other ADS Concepts

| Concept | Boundary and role | What it is not |
|---|---|---|
| Workspace Interface | A provider-owned, versioned public contract for cross-workspace interaction and published information. | It is not a directory, private storage view, or implicit permission grant. |
| Capability | A stable contract for a bounded function used by a workspace. | It is not automatically an externally invocable API or a cross-workspace authority boundary. |
| Capability Implementation | A concrete realization of a Capability. | It is not the public interface contract, even when an adapter uses it. |
| Workflow | A provider-owned, reusable route with an entry contract, stages, acceptance, and transition rules that performs work within declared authority. | It is not exposed wholesale merely because one operation delegates to it, and it is not automatically a Capability. |
| Interface Binding | Consumer configuration selecting a provider interface version and allowed operations. | It is not a Capability Binding and does not bind directly to provider storage. |
| Direct storage access | Reading another workspace's files, context, bindings, drafts, or run state. | It is not a valid cross-workspace integration. |

An interface may expose a workflow operation, and a workflow may invoke a local
Capability Implementation, but these remain separate contracts. The interface
defines what is safe and public at the boundary; the provider remains free to
change its internal workflow and implementation while preserving the interface's
compatibility promises.

## Parent and Child Workspaces

Parent and child relationships do not create shared storage or inherited private
access. A child may add context sources, Capabilities, Capability Implementations,
bindings, and workflows for its own purpose. Those additions remain local and
private unless the child publishes them through an interface.

A parent may provide shared direction, constraints, or authority through a declared
interface operation. A child may return a status summary, result, evidence summary,
accepted artifact, or explicit handoff through its interface. The parent sees only
what the child contract publishes and does not inspect the child's drafts or run
state to fill gaps in the contract.

The same rule applies in the other direction: a child consumes parent-owned
information only when the parent publishes it through an interface, published
context, accepted artifact, or explicit handoff. A parent may not reach into a
child's private implementation merely because it created or owns the child
workspace.

## Example Interface Manifest

The following is a transport-neutral example. The `input` and `output` entries are
contract descriptions, not a requirement to use a particular schema language.

```yaml
interface:
  interface_id: quality-review.document-review
  provider_workspace: quality-review
  contract_version: 1.0.0
  lifecycle: active
  owner: quality-review-owner
  maintenance: quality-review-maintainers

  audience:
    - consumer: delivery
      relationship: parent
      operations: [submit-review, get-status]

  authority:
    provider_must_allow:
      - create review runs in quality-review
      - publish review evidence summaries
    consumer_must_provide:
      - authority to submit the referenced artifact for review
    not_delegated:
      - acceptance of the delivery workspace's final release
      - promotion into delivery's authoritative repository

  operations:
    - operation_id: submit-review
      kind: command
      execution: asynchronous
      side_effects:
        - creates a private provider run
        - may publish an accepted review report
      idempotency:
        required: true
        duplicate_behavior: return-original-invocation
      input:
        required:
          - request_id
          - idempotency_key
          - artifact_ref
          - review_criteria_version
        artifact_ref:
          accepts: published-context-or-accepted-artifact
          rejects: provider-private-filesystem-path
      public_status: [acknowledged, in_progress, completed, failed, rejected]
      output:
        completed:
          - review_id
          - findings_summary
          - evidence_summary_ref
          - accepted_report_ref
          - handoff
        failed:
          - failure_code
          - retryable
          - committed_effects
          - next_action

    - operation_id: get-status
      kind: read
      execution: synchronous
      side_effects: []
      input:
        required: [request_id-or-review_id]
      output:
        - public_status
        - safe_summary
        - last_updated
        - published_output_refs

  private_by_default:
    - raw context assembled for the review
    - private prompts and internal instructions
    - raw tool calls and internal logs
    - Capability Implementations and bindings
    - unaccepted drafts and private run state

  published_artifacts:
    - evidence_summary
    - accepted_review_report
  compatibility:
    breaking_change_requires: new-major-contract-version
```

This manifest does not create a workspace snapshot. Each provider or consumer run
retains the interface contract version, relevant workflow and Capability versions,
input references, and published output references needed for provenance.

## Change and Compatibility

The provider owns interface maintenance and announces material changes. A change
to operation identity, required input, output meaning, authority, side effects,
failure semantics, privacy, or idempotency is a contract change even if the
transport is unchanged. The provider either publishes a compatible version with a
migration path or publishes a new contract version and manages the old version's
deprecation.

Changing a transport adapter, internal workflow, Capability Implementation, or
private storage layout is not by itself an interface change when the declared
contract and published behavior remain compatible.
