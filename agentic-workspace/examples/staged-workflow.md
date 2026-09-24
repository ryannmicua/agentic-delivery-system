# Staged Workflow Example: Documentation Release

This example shows one way to describe a workflow with artifact handoffs. Its
stages, headings, and storage choices are illustrative, not required by the
workspace model.

## Entry route

**Use when:** A release changes published product guidance.

**Outcome:** The published guide reflects verified release behavior, and the
release issue points to the result and its checks.

**Start with:** The release issue, the current guide, the source of verified
product facts, and the applicable writing guidance. Link to those maintained
sources from the real workflow entry point. Use the issue as the run record.

## Stages and handoffs

### 1. Correct the guide

- **Input:** Release issue, verified product facts, current guide, and writing guidance.
- **Action:** Revise the affected guidance.
- **Output:** Draft revision in the documentation branch, linked from the issue.
- **Check:** Compare changed claims with the verified facts and record the result.
- **Handoff:** Send the draft and check result for review.

### 2. Review the change

- **Input:** Draft revision and its check result.
- **Action:** Review the draft against the release issue and writing guidance.
- **Output:** Approval or requested changes, with the reviewer and decision recorded
  in the issue.
- **Handoff:** Return requested changes to correction, or send the approved
  revision to publication.

### 3. Publish

- **Input:** Approved revision and publishing instructions.
- **Action:** Publish the approved change.
- **Output:** Live guide linked from the issue.
- **Check:** Confirm the live page contains the approved change and record the
  confirmation in the issue.

The review stage can return to correction. Each stage follows a reusable
procedure if one exists; the workflow records how the stages connect rather
than repeating their detailed instructions.

## Run record

The issue retains material decisions, stage results, evidence, and the next
intended action. Before publication, record the intended external change as
pending. Afterward, record the confirmed live result or mark its outcome
uncertain. On resumption, inspect the live page before retrying publication.
This lets an actor continue without relying on a nonempty output folder as proof
that a stage was completed.
