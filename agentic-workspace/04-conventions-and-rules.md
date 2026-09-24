# Conventions and Core Rules

Core rules describe required behavior. Conventions are recommended defaults that
practitioners may adopt, adapt, or replace while preserving that behavior.
Templates illustrate one way to implement the model; their layouts, headings,
filenames, and tools are not requirements.

The concepts and principles explain the rules' intent. Conformance is determined
by whether an implementation preserves the core rules below, not by whether it
copies this package's examples. Neither a particular filesystem nor a runtime is
required.

## Core rules

1. **Provide a discoverable entry point.** It explains the workspace purpose and
   routes actors to context, capabilities, and work locations.
2. **Select context for the task.** Retrieve enough to support the next action;
   investigate material gaps instead of silently inventing missing facts.
3. **Preserve meaningful source distinctions.** Keep material claims traceable
   and distinguish instructions, facts, assumptions, and examples.
4. **Resolve overrides explicitly.** Apply specific choices to defaults without
   silently removing constraints or hiding factual contradictions. Follow the
   behavioral distinctions in [Context](02-context.md). Its suggested ordering of
   defaults may be replaced by another explicit, consistent resolution convention.
5. **Respect actual operating boundaries.** Use the permissions and instructions
   already applicable to the actor and systems. Tool availability alone does not
   authorize an action. The workspace need not create another permission system.
6. **Connect actions to an outcome and a check.** Know what the task is trying to
   achieve and check the result proportionately. State failures and uncertainty.
7. **Leave ticketed work traceable.** Any work performed under a ticket, whether
   or not it is part of a named workflow, must leave an activity and change
   audit trail in the existing ticket or linked work record. Capture each
   material action, who or what performed it and when, capabilities used,
   systems or artifacts inspected or changed, outcomes, handoffs, and evidence
   as work proceeds. Identify each affected resource and its resulting state, or
   link to a record that does.
   Include failed or no-change attempts when material, and state when the ticket
   resulted in no change. Link detailed system audit records when required by
   local policy; do not copy secrets or unnecessary sensitive values. Keep enough
   context to understand decisions, find results, and resume unfinished work.
8. **Keep sources aligned with verified reality and learning.** Update the
   authoritative source when verified facts change, or make a discrepancy
   visible when the source cannot be changed. Preserve the distinction between
   intended and observed state. Keep shared guidance at its designated home and
   promote durable learning from runs there; leave one-off details in the work
   record.
9. **Organize for correct outcomes.** Derive the simplest useful arrangement of
   information, capabilities, work records, handoffs, and checks from
   representative tasks. Evaluate whether intended humans and agents can
   complete those tasks correctly and maintain documented state against verified
   reality.
10. **Make runs restart-safe.** Keep the goal, material decisions, completed
    actions and evidence, next intended action, and uncertain external outcomes
    in a durable recovery record. Before a consequential external action, record
    the intended action as pending; afterward record its confirmed outcome or
    retain its uncertain status. On restart, read the record and inspect current
    external state; reconcile uncertain actions before retrying. Use operation
    IDs, idempotent actions, or a current-state or audit-history check to avoid
    duplicate effects and stale assumptions. Delay action when its outcome cannot
    yet be established safely.

## Conventions

- Prefer short Markdown documents and ordinary links where they fit the environment.
- Use the same shared content for human and AI actors; keep runtime-specific
  entry files thin.
- Describe routes by question or task, with a reason to follow each important link.
- Keep the initial context small. Put detailed material behind relevant routes.
- Reuse existing tools and work records before adding new storage or infrastructure.
- Keep task outputs separate from reusable instructions when they share a folder.
- Add procedures for recurring tasks and workflows when connecting procedures or
  stages is useful. Add further structure for demonstrated needs.

## Deliberate implementation choices

Implementers choose names, file locations, retrieval tools, and work tracking
systems. A one-document workspace is valid when it supplies the necessary routes
and behavior. A workspace spanning several systems is also valid.

Recommended layouts, templates, and tools can be adopted, adapted, or replaced.
For example, an application landing page can provide the entry point and context
routes shown as a Markdown file in the example. The required behavior is that
actors can discover and use those routes; the file itself is optional.

No formal capability registry, versioned inter-workspace interface, universal
readiness gates, mandatory context snapshot, or isolated run store is required.
Such mechanisms may be introduced locally when they solve a concrete problem;
they are not hidden conditions for adopting this baseline.
