# Workspace

## Definition

A workspace is the operating environment for a coherent kind of work. It contains one
or more Agentic Workflows and makes the context, authority, capabilities, and working
state needed for those workflows available at the right time.

A workspace enables humans and agents to:

- surface relevant context;
- retrieve and scope that context for the current task;
- consume context through workflows and capabilities;
- record working results, decisions, evidence, and handoffs;
- return accepted results to authoritative locations.

```text
Workspace
  = Kernel
  + Context surfaces and routes
  + Authority boundaries
  + Capabilities, Capability Implementations, and Bindings
  + Workflows
  + Public interfaces and interface bindings
  + Working state
```

A workspace is more than a folder. Its files, systems, and runtime integrations implement an operating contract. That contract defines what the workspace is for, what context it can use, what may happen within it, how work is performed, and how results become trusted.

## Workspace Role

The workspace connects intent to execution. It identifies the relevant context, makes the available capabilities visible, applies authority boundaries, and provides the places where work and results are recorded.

Capabilities define bounded functions. Capability Implementations realize those
functions locally or externally. Bindings connect selected implementations to
workspace requirements. Workflows compose them into repeatable paths. Public
interfaces expose selected workspace operations and published information to
declared consumers. Runs hold the request-specific state produced by one execution.

The workspace does not grant authority merely because a Capability Implementation or
binding is available. It declares what may be read, changed, decided, accepted, and
promoted. A first implementation may use lightweight boundary rules rather than a
full permission system, but it must still declare ownership, allowed actors,
resource boundaries, and acceptance and promotion responsibilities.

Child workspaces may introduce new context sources, Capabilities, Capability
Implementations, bindings, and workflows. These additions are local and private by
default. They do not become visible to a parent or sibling workspace unless the
child explicitly exposes them through a public interface.

The model does not require a separate workspace-snapshot object. A run records the
workspace, workflow, interface, and Capability Implementation versions and context
references needed to explain what it used. New runs resolve the current definitions;
an active run must not silently change its referenced definitions or bindings.

## Workspace Kernel

The workspace kernel is the minimum contract that makes a workspace understandable, governable, and maintainable.

It answers six questions:

1. **What is this workspace?**  
   Its purpose, scope, ownership, and boundaries.

2. **Where is its context?**  
   Its authoritative sources and request routes.

3. **What may happen here?**  
   Its access, authority, delegated decisions, retained decisions, and stop conditions.

4. **What Capabilities and implementations are available?**  
   Its required Capabilities, selected Capability Implementations, contract and
   implementation versions, and bindings.

5. **How is work performed?**  
   Its workflows, runs, and working-state locations.

6. **How are results trusted and maintained?**  
   Its evidence, acceptance, promotion, ownership, and maintenance arrangements.

## Minimum Workspace Information

Every workspace declares:

- name and purpose;
- what it owns and does not own;
- parent and child relationships;
- owner and maintenance responsibility;
- context sources and routes;
- accessible systems and data;
- allowed capabilities and decisions;
- retained human decisions;
- required Capabilities;
- selected Capability Implementations and bindings;
- available workflows;
- public interfaces and their declared consumers;
- working-state locations;
- acceptance and promotion rules;
- escalation and stop conditions.

Workspace-to-workspace access is only through a versioned public interface. A
workspace must not read another workspace's private context, files, bindings,
working artifacts, drafts, or run state directly. Parent and child relationships do
not create an exception to this boundary.

## Public Interfaces

A [Workspace Interface](07-workspace-interface.md) is a versioned contract for
interaction across a workspace boundary. It declares, at minimum:

- interface identity, owner, and version;
- intended consumers or audience;
- operations or workflows it exposes;
- input and output contracts;
- whether it exposes in-progress status;
- failure and retry behavior;
- side effects and their authority requirements;
- results, evidence summaries, accepted artifacts, or handoffs it may publish; and
- information it keeps private.

An interface may be implemented by a local adapter, file exchange, service, or
message channel. The transport is an implementation detail. The consumer binds to
the interface contract, not to the provider's internal storage or Capability
Implementations.

Public interfaces may expose:

- request acknowledgement and in-progress status;
- completed results;
- declared failures and escalation requirements;
- evidence summaries and explicit handoffs; and
- accepted artifacts made available for the consumer.

They must not expose private run state, private context, unaccepted working drafts,
or internal bindings unless the interface explicitly defines a governed operation for
that information.

The interface contract defines the operation lifecycle, Interface Binding,
invocation, retry and idempotency behavior, authority boundary, and compatibility
rules. The provider may change its internal workflow or Capability Implementation
without exposing those internals when the interface contract remains compatible.

## Logical Roots

A workspace identifies logical roots for context, workflow definitions, runs, accepted artifacts, evaluations, and maintenance. The physical locations are configurable and may be local or external.

A recommended scaffold may use standard folders, but the folder tree is not the architecture.
Cross-workspace references must resolve to a public interface, published context,
accepted artifact, or explicit handoff rather than another workspace's physical root.

## Maintenance

Every workspace names a maintenance owner and a maintenance path. Shared maintenance normally comes from a parent maintenance workspace. A child workspace adds local maintenance only when its needs differ.

## Filesystem-backed Workspaces

A filesystem can implement a workspace when its folders and files provide the workspace contract. For example, layered routing files can surface context, workflow folders can hold reusable stage definitions and references, run folders can isolate request-specific records and artifacts, and interface manifests can describe the workspace's public boundary. A workflow stage folder is never the authoritative home for output from a run.

This pattern is historically informed by Interpretable Context Methodology (ICM), but
the model is not an ICM-specific workspace or workflow. Folders and markdown files are
one possible implementation and binding; the workspace remains the operating
environment, Capabilities define bounded functions, workflows define the sequence,
and isolated runs hold request-specific state. A consumer must use the provider's interface
binding rather than reaching into the provider's folders.
