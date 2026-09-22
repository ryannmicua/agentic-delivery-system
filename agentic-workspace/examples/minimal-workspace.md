# Minimal Workspace Example

This template illustrates one implementation, not a required layout. Adopt,
adapt, or replace its files, headings, and tools to suit the environment.
Conformance depends on preserving the [core rules](../04-conventions-and-rules.md),
not on reproducing this example.

This example uses a documentation repository. The paths inside the snippets are
illustrative; adapt them to verified locations before using the entry document.
It assumes the repository already contains a guide, product reference, and writing
guidance. For this example, add the workspace entry point and a route to it from
the entry files actors use. An existing landing page or application view could
serve the same purpose without adding a file.

## Example entry point: WORKSPACE.md

```markdown
# Product Documentation Workspace

Help maintain accurate instructions for people using the product. Work here
changes documentation; requests to change product behavior belong in the product
repository.

## Find context

| Task or question | Start here |
|---|---|
| Understand the requested change | The current request or linked issue; clarify the affected reader and outcome. |
| Find current user instructions | docs/user-guide.md — the published guide's source. |
| Understand intended product behavior | docs/product-reference.md — the maintained specification; discrepancies with observed behavior need investigation. |
| Follow writing conventions | docs/writing.md — shared terminology and style guidance. |

Read the relevant sections, then follow their links if the task needs more detail.
Do not load the entire documentation tree by default.

## Available capabilities

- Repository search: use the editor search or rg to locate affected instructions.
- Markdown editing: edit the guide in the repository using the available editor.
- Product clarification: identify unanswered behavior questions in the work record
  and ask the requester for the relevant source or contact.

## Start and retain work

Start from a request identifying the reader's problem or the needed correction.
Use the existing issue or task conversation to retain decisions and the result.
Edit the relevant guide section. Keep exploratory drafts in the task's working
location if needed; do not treat them as published instructions.

## Defaults and constraints

Default: follow the guide's existing structure and writing style. A task may
request a different presentation while retaining required terminology.

Constraint: do not state that the product supports a behavior without a supporting
source or observation. Surface unresolved discrepancies with product references.

Repository access and review rules continue to apply.

## Finish

Compare the changed instructions with their supporting source, check that links
resolve, and read the result as someone trying to follow the procedure. Report
what changed and any step you could not verify. The repository's existing
publication process determines when the guide is published.
```

## Optional procedure: correcting a guide

Add this only when the procedure is useful enough to reuse. Link to it from the
entry point's "Start and retain work" section using its actual location.

```markdown
# Correct a User Guide

## Use when

A reader reports an inaccurate or incomplete instruction.

## Start with

The reported problem and affected guide section. Follow the workspace routes for
product behavior and writing guidance.

## Steps

1. Understand what the reader is trying to do and locate the affected instructions.
2. Compare them with the relevant product source or observation. If behavior is
   unresolved, record the discrepancy and ask the specific question needed.
3. Make the correction and inspect related references for inconsistencies.
4. Check the correction against the source and read through the resulting procedure.

## Result

The corrected guide section in its existing location, with material rationale and
source references in the issue or task conversation.

## Check

The correction addresses the reported problem, agrees with supported behavior,
and has usable references. State whether the procedure was actually exercised;
a document comparison alone does not establish that the product works as described.
```

## How task-specific context works

A request to fix a broken link needs the affected page and a verified destination.
It does not need the full product specification. A request to correct a setup
procedure may also need the relevant specification and an observed product result.

A request for a checklist can override a prose-format default. A request claiming
that a feature exists does not override the need to verify that claim. If sources
disagree, the task record retains the discrepancy until it is resolved.

Both tasks can use the same entry point and ordinary work records. Neither needs
a separate context manifest or run directory.
