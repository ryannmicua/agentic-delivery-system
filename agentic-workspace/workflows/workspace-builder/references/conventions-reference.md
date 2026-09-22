# Workspace Builder Conventions Reference

The ADS documents are authoritative. This file is a stage-scoped index and translation
guide for the workspace-builder workflow; it must not redefine the core model.

## Read for the active task

- Workspace minimum contract and authority: `../../../02-workspace.md`.
- Workflow and run contracts: `../../../08-workflows-and-runs.md`.
- Workspace-wide rules: `../../../04-workspace-conventions.md` and `../../../06-general-rules.md`.
- Capability contracts and bindings: `../../../03-capabilities.md` and `../../../05-capability-conventions.md`.
- Public boundary rules: `../../../07-workspace-interface.md`.

## Translation of the source workflow

The source workflow uses a five-stage pipeline and stage-local `output/` folders.
In ADS, the five stages remain the same, but request-specific outputs move under the
isolated run. The reusable workflow owns stage definitions; a run owns the workflow
map, contracts, candidate scaffold, questionnaire, validation report, and evidence.

| Source concern | ADS form |
|---|---|
| Workspace entry and task routing | Workflow entry contract and stage table |
| Stage `CONTEXT.md` | Reusable numbered stage definition |
| Stage-local `output/` | `runs/<run-id>/artifacts/<stage>/` |
| Shared references | Workflow-scoped references resolved through Context Provider and Assembly |
| User checkpoint | Interaction record plus evaluated transition |
| Convention audit | Evaluation against the ADS acceptance snapshot |
| Generated workspace | Unaccepted candidate artifact until promotion |

## Rules to apply

1. Keep one organizing purpose and one authoritative home for each durable fact.
2. Make stage Inputs, Process, Outputs, completion, authority, and failure behavior inspectable.
3. Keep cross-references one-way and record a dependency graph before scaffolding.
4. Keep context, Capability bindings, authority, interfaces, and maintenance explicit.
5. Use placeholders only for values supplied by the workspace owner or a run; do not hide policy in a placeholder.
6. Keep definitions separate from run state. Do not write run artifacts into `workflows/workspace-builder/stages/`.
7. Treat generated files as working output until evaluation and acceptance pass.
8. Do not infer authority, acceptance, promotion, or cross-workspace access from a tool or folder's existence.
