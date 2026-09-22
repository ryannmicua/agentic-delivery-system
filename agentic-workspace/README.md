# Agentic Workspace

Status: Approved baseline. The current contents of this package are approved.

An agentic workspace helps humans and AI agents understand the situation, identify
what needs to change, and use available capabilities to produce and verify that
change.

It provides a context-aware environment for work. Its value is how reliably an
actor can find relevant information and act on it, with little setup or ceremony.

This package defines principles, conventions, and core rules. Implementation
remains the practitioner's choice. Conformance depends on preserving the required
behavior, not copying a directory layout, template, or tool selection.

- **Principles** explain the intent behind the model.
- **Core rules** define required behavior.
- **Conventions** provide recommended defaults that may be adapted or replaced.
- **Templates and examples** illustrate possible implementations; they may be
  adopted, adapted, or replaced.

The [core rules](04-conventions-and-rules.md) are the behavioral baseline. Setup
guidance and examples do not add requirements through their format or structure.

## Three core concepts

| Concept | Question it answers |
|---|---|
| **Workspace** | What is this environment for, and where do I start? |
| **Context** | What do I need to understand for this task, and where can I find it? |
| **Work** | What needs to change, how will I do it, and how will I check the result? |

Work includes actions, reusable procedures, workflows, runs, and outputs. Procedures
describe how to perform a kind of task; workflows connect procedures or stages
toward an outcome. A task can begin without either. Capabilities are the available means of doing
work: people, skills, tools, services, or combinations of them.

The basic loop is:

```text
Understand the request -> Discover enough context -> Act -> Check the result
                                ^                    |            |
                                +--------------------+------------+
                                                      |
                                      Update the relevant source of truth
```

New information can change the understanding of the problem or the next action.
The loop describes useful behavior; it does not require stage records or gates.

## Reading order

1. [Workspace](01-workspace.md): the environment and its entry point.
2. [Context](02-context.md): sources, discovery, resolution, and assembly.
3. [Work](03-work.md): tasks, capabilities, procedures, workflows, runs, and results.
4. [Conventions and core rules](04-conventions-and-rules.md): what implementations
   must preserve and what they may choose.
5. [Standing up a workspace](05-standing-up-a-workspace.md): setup and a practical
   usability check.
6. [Minimal example](examples/minimal-workspace.md): a copyable entry document and
   an optional procedure.

Implementing agents should read the five short core documents before designing a
workspace. Actors using an established workspace start at its entry point and
follow only the routes needed for their task.

## Scope

This package is self-contained. It does not require the previous workspace model
or the team package to implement it. The team model's real-world context, problem
space, and capability questions inform the approach; its readiness gates and
other operating practices are not prerequisites.

A workspace can start with one short entry document pointing to existing
resources. There is no required runtime, folder structure, capability registry,
interface layer, approval process, or separate run database. Add structure when
actual work needs it.
