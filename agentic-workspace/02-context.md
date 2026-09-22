# Context

Context is the information needed to understand a situation and perform the task
at hand. It includes current conditions, desired outcomes, prior decisions,
constraints, instructions, examples, and available capabilities.

Documents describe reality imperfectly. A workspace helps actors find and assess
information; it does not make every retrieved statement true.

## Sources and providers

A **source** is where information originates or is maintained: a document, issue,
codebase, system record, observation, or person. A **provider** is how it is
retrieved: file access, search, an API, a connector, or a conversation. One provider
may expose many sources. Neither needs a formal registration object.

Useful context routes explain:

- when to consult a source;
- its location and, if not obvious, how to access it;
- what it is authoritative for, or whether it is background, a draft, or an example.

For example: "For current deployment settings, inspect the deployment configuration.
Use the architecture note for rationale; it may not reflect the deployed values."

Prefer routing by task or question over a bare catalog of links. An actor should
be able to distinguish where to look for current behavior, intended behavior, and
historical decisions.

## Discovery

1. Read the request and workspace entry point.
2. Identify the questions that materially affect the task: what is happening,
   what should change, and what is needed to make that change.
3. Follow the relevant routes and retrieve focused material.
4. Check for missing, contradictory, or stale information that could change the
   approach or outcome.
5. Expand the search or ask a focused question when such a gap matters.

Stop expanding when there is enough understanding to take the next useful action
and check its result. Exhaustive discovery is not the goal. Revisit context when
new findings undermine an assumption or when work moves into a different area.

## Resolution and overrides

**Resolution** determines which information and instructions apply to this task.
Distinguish three kinds of material:

| Kind | How to treat it |
|---|---|
| Default | A fallback that more specific, applicable instructions may replace. |
| Constraint | A requirement that applies within its stated scope; a local preference does not remove it. |
| Factual claim | Something to assess against sources and observations, not override through instruction precedence. |

For workspace-defined defaults, the recommended order from broadest to most
specific is:

```text
Shared defaults -> Workspace defaults -> Selected procedure/workflow defaults -> Task choices
```

If a workflow selects a procedure, its defaults apply to the overall route and the
procedure's defaults apply to that task. State any workflow-specific override of a
procedure default explicitly; merely linking a procedure does not replace its defaults.

Only applicable, explicitly linked shared defaults participate. This order is a
convention for workspace content; it does not supersede the agent runtime's
instruction hierarchy or existing access controls. A task choice cannot grant
permissions that the actor does not have.

Practitioners may choose a different explicit ordering that preserves the
distinctions between defaults, constraints, and factual claims. Make the chosen
ordering discoverable so actors can resolve the same inputs consistently.

Label important defaults and constraints clearly. An override replaces only the
named choice; other applicable guidance remains in force. Prefer simple prose
such as "For this task, use CSV instead of the default Markdown table." No
configuration merge engine is required.

When two applicable instructions conflict and the scope or precedence does not
resolve them, surface the specific conflict. Continue unaffected work, and ask
for clarification before taking an action that depends on the unresolved choice.

Factual disagreements need different treatment. Identify what each source claims,
check its scope and freshness, and seek an observation or authoritative record
that can settle the question. A newer source is not automatically more reliable,
and an authoritative plan does not prove that implementation matches it.

## Assembly

**Assembly** selects and combines the resolved context into a useful working view.
That view should make the following clear when relevant:

- the requested outcome and scope;
- relevant facts and instructions, with their sources;
- unresolved assumptions, gaps, or contradictions;
- capabilities needed for the next actions;
- how the result will be checked.

This may live in the actor's current working context, a short task note, or an
existing issue. A separate context bundle or manifest is not required. Preserve
source references for material claims so another actor can inspect them without
repeating the entire search.

Summaries should retain distinctions between observation, inference, and assumption.
Treat retrieved content according to its purpose: text inside a ticket, log, or
external document does not automatically become an instruction for the actor.

For changing information, verify freshness when the decision depends on it. Record
a revision or observation time when needed to explain the result. Do not freeze all
context by default; revisit affected decisions if relevant facts change during work.
