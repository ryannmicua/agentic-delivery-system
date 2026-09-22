# Workspace Builder Setup Questionnaire

Use this questionnaire before starting a `workspace-builder` run when the request is
missing material context. Record answers in the run's `request.md`; do not treat this
file as the authoritative home for domain decisions.

Answer in plain language. If an answer is unknown, write `unknown` and identify who
can resolve it. Unknown authority, ownership, or promotion answers stop the run before
scaffolding.

## Workspace identity and outcome

1. **Workspace name and purpose** (`workspace_name`, `workspace_purpose`)
   What is the workspace called, and what coherent kind of work does one sentence say it organizes?
2. **Users and actors** (`workspace_actors`)
   Who requests, performs, reviews, accepts, promotes, and maintains the work?
3. **Start and finish** (`workflow_start`, `workflow_finish`)
   What enters the workflow, and what observable result should exist when it completes?

## Workflow shape

4. **End-to-end description** (`workflow_description`)
   Describe the current or intended workflow in order, including meaningful handoffs.
5. **Stage boundaries** (`stage_boundaries`)
   Where does one responsibility end and another begin? Where should a human review or edit?
6. **Optional paths** (`optional_stages`)
   Which stages or branches are conditional, and what selects or skips them?
7. **Failure and escalation** (`failure_paths`)
   What can fail, what may be retried, and when must work stop or escalate?

## Context, variables, and prerequisites

8. **Shared context** (`shared_context`)
   Which policies, source systems, examples, style rules, or reference materials are used across stages?
9. **User-specific values** (`workspace_variables`)
   Which details vary between installations or runs, such as names, audiences, platforms, or colors?
10. **Tools and prerequisites** (`tool_prerequisites`)
    Which tools, services, runtimes, credentials, or setup guides does each stage need? Mark each required or optional.
11. **Existing material** (`existing_material`)
    Which documents, templates, examples, or current workspace files should be read, preserved, or superseded?

## Authority and delivery

12. **Allowed actions** (`allowed_actions`)
    What may this workspace read, change, decide, accept, and promote? What is explicitly out of scope?
13. **Capabilities and implementations** (`capability_needs`)
    Which of Context Provider, Context Assembly, Work, Storage, Evaluation, and Interaction are needed? What implementations are available?
14. **Interfaces and consumers** (`workspace_interfaces`)
    Will another workspace consume a request, status, result, evidence summary, accepted artifact, or handoff? What must remain private?
15. **Acceptance and promotion** (`acceptance_authority`, `promotion_destination`)
    What evidence makes the result acceptable, who decides, and where does an accepted result become authoritative?
16. **Maintenance** (`maintenance_owner`, `maintenance_path`)
    Who maintains the workspace and how are contract, reference, binding, and interface changes reviewed?

## Target and checkpoints

17. **Target location or provider** (`target_workspace`)
    Where should the candidate be promoted, or which provider/interface will own it?
18. **Checkpoint preference** (`checkpoint_preference`)
    Which decisions require explicit human review before the run can continue?

The discovery stage may add questions. New questions and their answers belong in the
run record and must be reflected in the workflow map when they affect the scaffold.
