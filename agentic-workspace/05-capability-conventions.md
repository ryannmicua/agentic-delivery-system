# Capability Conventions

These conventions apply to Capabilities, Capability Implementations, and the
workspaces that use them.

## 1. Define the Capability before choosing the implementation

A workflow declares the Capabilities it requires. The workspace may satisfy those
requirements with local or external Capability Implementations.

## 2. Keep one authoritative contract per Capability

Each Capability has one authoritative definition for its purpose, contract version,
boundaries, required authority, and conformance expectations. Implementations may
differ without changing that definition.

## 3. Bind explicitly

Connect every required Capability to the Capability Implementation used by the
workspace. The binding identifies the implementation source, identity, version when
available, configuration, and status. Do not imply a binding merely because a tool,
file, or service is present.

## 4. Version contracts and implementations separately

Record the Capability contract version and the Capability Implementation identity and
version separately. A change to a contract is not the same as an implementation
upgrade. A run must not silently change either one while work is in progress.

## 5. Configure without redefining

Workspace configuration may select options, limits, routes, or bindings. It must not
change the essential meaning, boundary, authority model, or result semantics of the
Capability.

## 6. Declare the shared contract

Every Capability and Capability Implementation declares, at minimum:

- Capability name and contract version;
- purpose and scope;
- inputs, outputs, and required context;
- required authority and permissions;
- side effects and failure behavior;
- provenance; and
- owner, maintenance path, and conformance checks.

## 7. Use implementation profiles for operational details

Declare caching, retries, concurrency, durability, cancellation, resource limits, and
similar operational behavior in the Capability Implementation profile when relevant.
These details must not be assumed merely from the Capability.

## 8. Declare effects and recovery

State whether an implementation reads or changes external systems, whether actions are
reversible or retry-safe, and how timeout, denial, partial completion, conflict, and
other failures are reported or recovered.

## 9. Provide conformance checks

Define how a consumer verifies that the Capability Implementation is available,
correctly bound, authorized, and producing results that satisfy the Capability
contract. Local terms such as "component," "action," or "process" do not replace the
formal Capability Implementation contract.

## 10. Preserve provenance

When a Capability contributes to consequential work, the binding and run record the
Capability name and contract version, Capability Implementation identity and version
when available, configuration, authority context, executor or actor, and result.

## 11. Change deliberately

Upgrade, replace, deprecate, or remove a Capability contract or Capability
Implementation through an explicit maintenance action. Record compatibility,
migration, and any effect on active bindings or runs.

## 12. Never grant authority

A Capability Implementation provides a bounded function. The workspace grants
authority. No Capability or implementation may expand its own access, permissions,
decision rights, acceptance rights, or promotion rights.

## 13. Keep Context Provider and Context Assembly distinct when useful

Context Provider provides source-backed material. Context Assembly selects and combines
task-scoped material. Keep them separate when multiple sources, conflicts, freshness,
privacy or authority filtering, or task-specific relevance make the distinction useful.
One Capability Implementation may provide both in a simple workspace; neither is a
mandatory stage.

## 14. Keep Capability results distinct from governance events

Retrieving context is not assembling all relevant context. Storing a result is not
accepting or promoting it. Evaluating a result is not accepting or promoting it.
Requesting approval or recording a response is not granting authority. Work may
participate in these activities only through an explicit workflow and the authority
declared by the workspace.
