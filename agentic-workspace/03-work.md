# Work

Work is the application of available capabilities to achieve a desired change.
It can be exploratory, one-off, or repeatable, and can be performed by humans,
AI agents, or mixed teams.

## Starting a task

Establish what needs to change, the scope, and what would count as a useful result.
Use the request and existing context; ask only when an unresolved question
materially affects the work. A small task can establish these points in a few
sentences. For exploratory work, the result may be an answered question or a
clear account of what remains unknown.

Select the capabilities needed for the task. A capability is an ability to do
something; its practical means may be a person, skill, tool, script, or service.
Make those means discoverable with enough information to use them. Do not require
a capability contract, implementation profile, and binding for each tool.

Verify availability when needed. If a capability is missing, use a suitable
available alternative or explain the gap. A documented tool is not necessarily
installed, accessible, or appropriate for the task.

## Actions, procedures, and workflows

An **action** is a unit of activity, such as inspecting a file, interviewing a
stakeholder, editing a document, or running a check.

A **procedure** is reusable instructions for a kind of task. It describes
when to use it, the actions to take, and how to recognize a satisfactory result.
Create one when repetition or complexity makes written guidance useful.

The following is a recommended procedure template. Its headings and format may
be adapted or replaced while keeping the instructions usable:

| Part | Content |
|---|---|
| Use when | The kind of task it supports. |
| Start with | Necessary inputs and relevant context routes. |
| Steps | A short sequence of actions, including needed capabilities. |
| Result | What to produce or change and where it belongs. |
| Check | How to determine whether the result meets the task's need. |

Include branches or stopping conditions only where the procedure needs them.
Steps may link to scripts, skills, or detailed instructions instead of restating
them. A procedure can be a single Markdown file; numbered stage directories and
an execution engine are optional implementation choices.

A **workflow** is a larger route connecting procedures or stages toward an outcome,
with handoffs or decisions between them. For example, a documentation release may
connect procedures for correcting guides, reviewing changes, and publishing the
release. Describe the connections and relevant decisions; link to the procedures
instead of duplicating their instructions.

When documenting a workflow, make it possible for an actor to find:

- when to use it and the outcome it aims to produce;
- the stages or procedures, their order or dependencies, and any optional paths;
- what each stage consumes and produces, where its result belongs, and how the
  result is checked before a handoff;
- who or what makes material decisions and where those decisions are recorded;
- the context and capabilities each stage needs, with links to their maintained
  sources; and
- where a run retains progress, evidence, and uncertain actions for safe resumption.

Describe only the parts the work needs. A workflow with several artifact handoffs
may use a short entry page linking to stage instructions, shared references, and
output locations. Keep reusable instructions separate from the results of a
particular run. The [staged workflow example](examples/staged-workflow.md) shows
one possible arrangement.

Procedures and workflows are optional. A task may use either, adapt its defaults,
or proceed without a predefined route. An adaptation still respects applicable
constraints and the requested outcome.

## Runs and outputs

A **run** is one occurrence of a procedure or workflow for a request. One-off work
can proceed as a task without being named or recorded as a run.

Use an existing conversation, issue, branch, task document, or application record
to retain the information needed to continue or understand the work. Keep the
request, material decisions, result location, and check outcome discoverable.
For short work these can be the request and final response; longer work may need
a persistent task note. A separate run ID, directory, or status schema is not
required if the existing system already distinguishes tasks adequately.

### Restart safety

Make each work run safe to resume from a fresh session. Keep a durable recovery
record, not only active-session context, with the goal, material decisions,
completed actions and evidence, next intended action, and any action whose
external outcome is uncertain. The ticket or existing task record may also
serve as this recovery record. Before a consequential external action, durably
record the intended action as pending; afterward record its confirmed outcome or
leave it marked uncertain. Include an operation ID when available. On restart,
read the record and inspect current state in relevant external systems before
continuing. Reconcile uncertain actions before retrying them. Use idempotent
actions where available; otherwise read current state or audit history before
repeating a consequential action. If evidence cannot settle whether it happened,
delay the action and use a safe recovery path. A restart should not lose work,
duplicate consequential changes, or silently accept stale state.

An **output** is material produced or changed during work. Edit the intended file
or system directly when that is the ordinary authorized way to do the task. Use
a draft, branch, or separate output location when review, concurrent work, or
experimentation makes that useful. Keep temporary task material distinguishable
from reusable procedure and workflow instructions.

## Checking and finishing

Choose a check appropriate to the requested change. Examples include executing
affected tests, comparing a document against its source, trying a procedure, or
confirming an updated system value. A claim of completion is not itself a check.

Any work performed under a ticket, whether or not it is part of a named workflow,
must leave an activity and change audit trail in the existing ticket or linked
work record. Record who or what performed each material action and when, the
actions and capabilities used, relevant systems or artifacts inspected or
changed, outcomes, handoffs, and evidence. For a change, identify the affected
resource and resulting state or link to a record that does; include failed or
no-change attempts when material. Capture the trail as work proceeds, and state
explicitly when the ticket resulted in no change.
Link to detailed system audit records when needed to meet local audit requirements;
do not copy secrets or unnecessary sensitive values into the ticket. The trail
must let an authorized reader understand what happened and find supporting
evidence.

Report what changed, where the result is, how it was checked, and any material
limitation. If the check fails or cannot be performed, say so and correct the
problem or identify what remains. Do not report an unverified outcome as verified.

Put durable results in the intended destination. Update related context when the
work changes facts or instructions that future tasks will depend on. A new
observation does not require a new knowledge document if it belongs in an existing
source.

When a run reveals durable learning, promote it to the appropriate existing
source of truth, standard, procedure, or other maintained guidance. Keep
one-off details in the work record; do not create a new knowledge artifact for
every ticket.

Checking, review, and publication can be distinct activities when the task needs
them. The baseline does not require separate acceptance or promotion machinery.
