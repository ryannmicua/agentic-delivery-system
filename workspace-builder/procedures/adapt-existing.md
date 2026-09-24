# Adapt an Existing Workspace

Use this procedure when a repository, shared folder, document system, or other
working environment already has useful entry points, instructions, sources, and
result locations, but its routes are incomplete or hard to follow.

This procedure applies the approved [Agentic Workspace baseline](../../agentic-workspace/README.md).
Use [discovery](../discovery.md) to gather the shared workspace facts; do not run
a separate questionnaire for adaptation.

## Start with the environment as it is

Choose one representative task that people or agents actually perform. From the
places those actors already encounter, inspect:

- the current entry mechanism, such as a README, instruction file, landing page,
  request queue, or application home;
- the access paths available to each intended actor, including runtime-loaded
  instructions and external systems;
- applicable instructions, defaults, constraints, and approval boundaries;
- sources used to understand current behavior, intended behavior, and prior
  decisions;
- capabilities used to perform and check the task; and
- the existing records and destinations for ongoing work and final results.

Confirm access by using the intended route when practical. A file that exists is
not necessarily loaded by an agent runtime, and a named service is not necessarily
available to every actor. Keep unverified access or facts marked as unknown.
Label any provisional design choices that depend on them as assumptions, and
check those dependencies before performing affected work.

## Map the representative task

Trace the task from request to checked result. For each question the actor must
answer, identify the existing source and state what it is authoritative for. For
each action, identify the applicable instructions, required capability, result
destination, and check.

Distinguish:

- authoritative sources from background, drafts, and examples;
- current observations from plans or historical decisions;
- constraints from defaults that a more specific choice may replace; and
- reusable instructions from records and outputs of this particular task.

Derive the workspace organization from this trace: where facts are maintained,
when current observations are needed, which views are derived, who can update
each source, and where outputs, handoffs, and ticket activity trails belong.
When a live fact changes, identify the authoritative source to update or the
discrepancy that must remain visible. Do not add an inventory or status tracker
merely to make the arrangement look complete.

Use the workspace's existing resolution convention when it is explicit and
consistent. Otherwise, use the baseline order of shared defaults, workspace
defaults, procedure or workflow defaults, and task choices. Include only shared
defaults that are explicitly linked and applicable. Existing runtime instruction
precedence and access controls still apply.

If applicable instructions conflict and scope or precedence does not settle the
conflict, name the exact choices and their sources. Continue work that does not
depend on the conflict. Seek a decision before taking only the affected action;
do not turn the conflict into a blanket approval gate.

## Make the smallest useful change

Prefer repairing a route over moving its source. Typical changes are:

- add or clarify a link from an entry point actors already use;
- say when to consult a source and what it governs;
- connect human and agent entry mechanisms to the same maintained guidance;
- document how to invoke an existing capability when that is unclear;
- identify the existing place for work records and results; or
- add a focused procedure only when recurring or complex work warrants it.

Keep authoritative material at its designated home and link to it. Do not copy
instructions into a new builder-owned document, reorganize the environment by
default, introduce a parallel work store, or create formal registries merely to
describe resources that are already discoverable. Change a source's location or
ownership only when the representative task demonstrates that routing alone will
not solve the problem.

When local guidance specializes a broader default, link the broader source and
state the precise local difference. An override changes only the named choice;
all other applicable guidance remains in force.

## Check the adaptation

Repeat the representative task from the entry point as the intended actor would.
Confirm that the actor can:

1. identify the requested outcome, scope, and actual constraints;
2. reach the relevant sources without reading unrelated material;
3. tell which sources are authoritative and which instructions apply;
4. find and use the needed capabilities within existing access;
5. locate the ordinary work record and result destination;
6. perform or identify a proportionate check of the result;
7. update the authoritative source with verified changes, or expose unresolved
   discrepancies between documented and observed state;
8. leave an activity and change audit trail for work under a ticket, with
   actors, actions, affected resources and resulting state, outcomes, and
   evidence, linking detailed system audit records when required;
9. identify the maintained home for durable learning revealed by the run; and
10. resume from its durable record and current external state, reconciling
    uncertain actions before retrying consequential changes.

Also verify that original task routes and applicable instructions still work.
Check links or access paths that were edited, and sample at least one route that
was intentionally preserved. If execution is inappropriate, perform a walkthrough
and say so; do not report it as an executed task.

The adaptation is complete when intended actors can understand, correctly
perform or credibly walk through, and check the representative task using
available capabilities; keep documentation aligned with verified reality or
expose a discrepancy; and leave a traceable ticket record where applicable.
Confirm an interrupted run can be recovered from its durable record and current
external state without losing work or repeating consequential changes. Report the
entry point, minimal changes, task tried, check outcome, assumptions, and any
unresolved limitation in the existing work record.
