# Standing Up a Workspace

Start from the work people actually need to do. The first implementation should
make one representative task easier to understand and complete.

This is a recommended setup approach, not a required implementation procedure.
Adapt its steps, layout, and tools to the environment. Preserve the
[core rules](04-conventions-and-rules.md) whichever approach you choose.

## 1. Inspect the existing environment

Identify its purpose, common requests, existing context sources, available
capabilities, and where results already live. Read applicable local instructions.
Prefer existing resources over new documents that repeat them.

Do not guess system access or invent organizational rules. Mark an unknown when
it affects setup; ask for clarification if it prevents a useful implementation.

## 2. Establish the entry point

Use the questions in [Workspace](01-workspace.md) or adapt the
[minimal example](examples/minimal-workspace.md). Keep the entry point short and
give each important context route a purpose.

Connect the entry point to the actual human and agent entry mechanisms. For a
repository this may mean linking it from README.md and the existing agent
instruction file. Preserve existing instructions when adding that route.

## 3. Make the routes usable

Verify that referenced files exist and that external sources can be reached by
the intended actor, or explain the access dependency. Identify what each source
is useful for. Add local defaults only where a choice is repeatedly needed.

Document the actual way to invoke relevant capabilities. A tool name without
usage guidance is sufficient only when its use is already clear in the environment.

## 4. Add a procedure only if useful

If the workspace has a recurring procedure, the five parts in [Work](03-work.md)
offer a useful template; adapt or replace that format as needed. Otherwise,
explain how a one-off request starts and where its
result should go. Do not manufacture a procedure to fill a template. Add a workflow
only when the work benefits from an explicit route connecting procedures or stages.

## 5. Try one representative task

Start from the entry point as a new actor would. Use an ordinary authorized task,
or walk through discovery and proposed actions if execution is not appropriate.
Check whether the actor can:

- identify the desired change and relevant scope;
- find useful context without reading unrelated material;
- distinguish current facts, defaults, constraints, and unresolved questions;
- locate the capabilities needed to act;
- identify the output destination and an appropriate result check.

Fix gaps the trial exposes. If a necessary source or capability is unavailable,
record the specific limitation rather than declaring the setup fully usable.
Report whether the trial included execution or only a walkthrough.

## Completion

The initial workspace is usable when its entry point and routes support the
representative task, required capabilities are available, and work has a clear
destination and check. Report the entry point, what was tried, and remaining
limitations. Empty scaffolding does not establish usability.

After that, let actual usage determine additions. A missed source suggests a
better route. Repeated steps may justify a procedure. Difficulty resuming work may
justify a task note. None automatically justifies an entire management layer.
