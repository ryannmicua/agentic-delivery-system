# Workspace Builder

Workspace Builder helps a human or AI actor create a usable agentic workspace or
improve an existing one. It diagnoses representative work, needed context,
source authority and freshness, actor access and capabilities, handoffs, records,
and result checks, then recommends the simplest effective organization. It
applies the approved
[Agentic Workspace baseline](../agentic-workspace/README.md) without changing it.
The builder is domain-neutral: the requester and the target environment supply
the domain facts, sources, constraints, and available capabilities.

Do not begin from a fixed folder taxonomy or treat a tidy structure as success.
Evaluate the workspace with representative tasks: can humans and agents complete
them correctly, keep documented state aligned with verified reality, leave an
activity and change audit trail for ticketed work, promote durable learning from
runs, and safely resume interrupted work without lost progress or duplicate
consequential changes?
The result is a discoverable entry point and only the organization the work needs.

## Choose a route

| Need | Route |
|---|---|
| Create a workspace for a new environment | [Greenfield procedure](procedures/greenfield.md) |
| Improve an environment that already has instructions, sources, or work practices | [Adapt-existing procedure](procedures/adapt-existing.md) |
| Decide what to write and how much detail to include | [Author guidance](procedures/author-guidance.md) |
| Establish missing requirements for either procedure | [Shared discovery](discovery.md) |
| Inspect evidence from building this package | [Dogfood check](checks/2026-09-23-dogfood.md) |

Both build procedures use the same focused discovery route. Do not replace it
with a separate questionnaire in each procedure.

## Context and authority

Start with the request, the target's entry point, and instructions that already
apply to the actor or target. Here, the root [AGENTS.md](../AGENTS.md) remains
applicable. Follow task-oriented routes to current behavior,
intended behavior, prior decisions, and constraints. Preserve authoritative
sources in place and link to them instead of copying their content into the new
workspace.

Resolve workspace-defined defaults using the baseline
[Context convention](../agentic-workspace/02-context.md):

```text
Shared defaults -> Workspace defaults -> Selected procedure or workflow defaults -> Task choices
```

This convention does not supersede runtime instructions, access controls, or
constraints. Treat factual claims as claims to verify, not settings to override.
If applicable instructions conflict, surface the specific conflict and continue
only with work that does not depend on it. Ask a focused question when an unknown
would materially change the workspace.

## Capabilities and access

- **Inspect and edit local content:** use the actor's file tools or editor; in a
  repository, start with `rg --files` and focused reads.
- **Resolve missing inputs:** ask the human or AI requester focused questions in
  the existing conversation or issue.
- **Reach external sources:** use a provider or connector only after verifying
  availability and the actor's access.
- **Check the result:** inspect Markdown and links, then execute or walk through a
  representative task from the target entry point.

Use only capabilities that are suitable and authorized; availability does not
grant permission. In the target entry point, state how to invoke capabilities
when that is unclear and record access limits that affect real tasks. A formal
capability registry or runtime-specific interface is unnecessary.

## Start a build

A useful request identifies the target environment, its purpose, and whether the
work is greenfield or an adaptation. Include known sources, recurring work, and
constraints when available; discovery will separate assumptions from questions
and fill only material gaps.

Use the existing conversation, issue, or task as the build record by default.
Keep the request, material decisions, result location, and check outcome there.
Create a separate task note only when the work is too long or distributed to
remain understandable in the existing record.

## Destinations and completion

Put the resulting entry point, routes, and any justified procedures in the target
workspace. Keep reusable builder instructions in this package. The local dogfood
check records evidence for this package's build only; it is not a required target
artifact or a template for every workspace.

Before finishing, check the result from the target entry point as a new actor
would. Confirm that the actor can:

- understand the workspace purpose, scope, and significant exclusions;
- route a representative task to relevant context without broad reading;
- distinguish authoritative facts, defaults, constraints, and open questions;
- find and invoke the capabilities needed for the task within actual access;
- start work and locate ongoing work and final results;
- identify a proportionate check for the result;
- keep documented state aligned with verified reality, or expose unresolved
  discrepancies;
- leave an activity and change audit trail for ticketed work, with references to
  supporting evidence or detailed system audit records where applicable;
- identify where durable learning from the task should be maintained;
- resume from the durable work record and current external state, reconciling
  uncertain actions before retrying them.

Report what changed, where it lives, what task was tried, the check outcome, and
any material limitation. A walkthrough is valid evidence when execution would be
inappropriate, but label it as a walkthrough.

## Constraints

- Preserve applicable target instructions and authoritative sources.
- Keep the baseline unchanged; specialize it through target-specific routes and
  defaults.
- Prefer the target's existing tools, records, and destinations.
- Do not impose a universal folder skeleton, registry, governance layer, or
  approval ceremony. Add local structure only for a concrete need.
- Keep human and AI routes aligned, with thin runtime-specific entry files when
  different runtimes require them.
