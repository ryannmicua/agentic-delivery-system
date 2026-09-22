# Workspace Conventions

These conventions apply to every workspace.

## 1. Give the workspace one organizing purpose

A workspace organizes one coherent kind of work. Its boundary must be explainable in one sentence.

Create a child workspace only when different context, authority, ownership, risk, or recurring work makes separation useful.

## 2. Use a small entry point

The workspace entry point states its purpose, boundaries, routes, authority, available work, and maintenance owner. It points to details instead of repeating them.

## 3. Route context progressively

Load only the context needed for the request. Name the source, authority, relevant scope, and reason for using it.

## 4. Keep authority explicit

Declare what the workspace may read, change, decide, execute, accept, and promote.
Authority may be represented by lightweight boundary rules in an initial
implementation; omitting the boundary altogether is not valid. A child workspace
may add local sources and Capabilities, but it may not access parent-owned or shared
resources except through an interface that grants that access.

## 5. Declare Capabilities and implementations

Record the Capabilities required by workflows, the selected Capability Implementations,
the contract and implementation versions, the binding, configuration, and status.
Binding an implementation does not grant permission to use it.

## 6. Keep workflows within the workspace boundary

A workflow may use only declared context, capabilities, and authority. It cannot grant itself new tools, access, approval rights, or promotion rights.

## 7. Make workflow contracts inspectable

Each reusable workflow declares a small entry contract, numbered stages for human
navigation, workflow-specific references, predefined acceptance measures, and rules for
transition, stop, and escalation. A route may select a workflow without turning the
workflow into a Capability. A workflow that implements a Capability must say so through
an explicit binding.

## 8. Keep workspace boundaries explicit

Context, Capabilities, Capability Implementations, bindings, workflows, and runs are
private to their workspace by default. Workspaces interact only through versioned
public interfaces defined by the [Workspace Interface](07-workspace-interface.md)
contract. Interfaces may expose acknowledgement, in-progress status, results,
failures, evidence summaries, accepted artifacts, and explicit handoffs. They do
not expose private storage or run state by default.

## 9. Isolate every run

A run has an explicit run ID and an isolated location. It keeps its request, resolved
context manifest, pinned acceptance snapshot, transition/status record, stage-organized
artifacts, evidence, failures, and decisions together. Run output never lives in a
workflow's stage-definition folders and does not overwrite reusable definitions or
authoritative context.

## 10. Promote results deliberately

Working outputs remain non-authoritative. Acceptance confirms that a result meets its standard. Promotion moves the accepted result to its authoritative destination.

## 11. Maintain the workspace

Review the workspace when its purpose, ownership, context, authority, Capabilities,
Capability Implementations, bindings, workflows, or parent policy changes. Record
material changes and migrations. Review public interface contracts when their
operations, inputs, outputs, exposed status, failure behavior, consumers, or
published artifacts change.
