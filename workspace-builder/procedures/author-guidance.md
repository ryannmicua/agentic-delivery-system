# Author Reusable Guidance

Use this procedure when repeated or complex work would benefit from maintained
instructions. It applies the approved [Agentic Workspace baseline](../../agentic-workspace/README.md).
Use [discovery](../discovery.md) for shared workspace facts, then follow existing
routes to the sources and constraints relevant to the work being documented.

## Decide what belongs in durable guidance

Choose the smallest form that makes future work easier:

| Form | Use it when |
|---|---|
| One-off task | The work is unlikely to repeat, or the route is still being learned. Keep decisions and results in the existing task or run record. |
| Procedure | A kind of task repeats, or its actions and check are easy to miss without written guidance. |
| Workflow | An outcome requires connected procedures or stages, with meaningful decisions or handoffs between them. |

Do not promote a single run into a procedure merely because it succeeded. Look
for stable actions, recurring decisions, or a costly failure that reusable
guidance would prevent. If the work is still exploratory, preserve the evidence
in the task record and wait for a repeatable pattern.

## Write a usable procedure

A reader should be able to determine:

- **When to use it:** the task type, relevant scope, and useful stopping
  conditions.
- **What it needs:** required inputs and focused routes to authoritative context.
- **What to do:** a compact sequence of actions, including branches that
  materially change the route.
- **What enables the work:** the people, skills, tools, scripts, or services
  needed, with links or invocation guidance where use is not obvious.
- **What results:** the expected change or output and its ordinary destination.
- **How to check it:** observable evidence that the result meets the task's need.
- **Where the activity trail goes:** for ticketed work, the existing ticket or
  linked work record must show who or what acted and when, actions taken,
  systems or artifacts inspected or changed, outcomes, handoffs, and evidence.
  Identify each affected resource and resulting state, or link to a record that
  does. Link detailed system audit records when local requirements call for them.

These are content needs, not required headings or a universal document skeleton.
Fit the procedure to the environment. Link to maintained source material and
detailed tool instructions instead of reproducing them. State defaults as
defaults and constraints as constraints. Keep examples compact and label them as
examples so they are not mistaken for current facts or mandatory structure.

For example, a procedure for updating a service guide might route the author to
the deployed configuration for current values and the architecture decision for
rationale, require editing the existing guide, and check every changed command
against a test environment. A particular service name, reviewer decision, test
URL, and changed-file list belong in that run's issue or task record rather than
in the reusable procedure.

## Write a workflow only when connections matter

A workflow should name its outcome and connect procedures or stages in the order
needed to reach it. Describe:

- entry conditions and the result expected at the end;
- links to procedures rather than copies of their steps;
- what each handoff carries and where the receiving actor finds it;
- decisions that select, repeat, pause, or stop a route; and
- an overall check when completing each procedure does not alone prove the
  workflow outcome.

Procedure defaults continue to apply when linked from a workflow. If the workflow
needs a different default, name that override explicitly and limit it to the
relevant scope. Do not silently weaken a constraint, treat a link as an override,
or add a universal approval stage. Include review, publication, or human choice
where the actual work requires it.

## Keep runs and outputs separate

Reusable guidance explains how a kind of work should proceed. A run or task
record retains what happened this time: the request, material assumptions and
decisions, selected branches or overrides, result locations, evidence, check
outcome, and unresolved limitations. Outputs go to the destination used by the
workspace, not into the procedure merely because the procedure produced them.

The existing conversation, issue, branch, application record, or task document
is sufficient when it leaves the work understandable. Any work under a ticket,
whether or not it follows a named workflow, needs an activity and change audit
trail in the existing ticket or linked work record. Record actor and time for
each material action, what was inspected or changed, the affected resource and
resulting state (or link to a record that shows it), outcomes, handoffs, and
evidence. Include failed or no-change attempts when material. Let authorized
readers follow what happened; link to system audit history where it carries the
detailed record. Follow local audit and data-handling requirements.
Do not create a run folder, identifier, or status model unless the environment
needs one.

Make the record usable after interruption: retain the goal, material decisions,
completed actions and evidence, next intended action, and uncertain outcomes.
Before a consequential external action, record the intent as pending; afterward,
record its confirmed result or keep it marked uncertain. When resuming, read the
record and inspect current external state before continuing. Reconcile pending or
uncertain actions before retrying. Use operation IDs or idempotent actions where
available, otherwise check current state or audit history; delay the action if
the outcome cannot yet be established safely.

After a run, update reusable guidance only when the experience reveals a durable
change: a recurring missing step, a stable decision rule, a moved authoritative
source, a changed capability, or a check that future actors need. Put factual
changes in their authoritative source and repair links as needed. Leave
task-specific choices and incidental observations in the task record. Promote
durable learning to its existing maintained home rather than creating a new
knowledge document for each ticket.

## Check the guidance

Try the procedure or workflow on a representative task, or walk it through when
execution is inappropriate. Confirm that a new intended actor can find the right
sources, use the available capabilities, follow material decisions and handoffs,
place results correctly, and determine whether the outcome is satisfactory. Also
check that a fresh actor can recover the run from its durable record and current
external state, and safely resolve an uncertain action before continuing.

Report whether the check was executed or walked through, what gaps were fixed,
and what remains uncertain. Guidance is ready when it supports the task without
duplicating authoritative content or mixing reusable instructions with one run's
decisions and outputs.
