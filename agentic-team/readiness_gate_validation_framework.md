# Readiness Gate Validation Framework

## Status

Working draft for refinement.

## Purpose

This framework defines how to determine whether the five default readiness gates are the right gates for agentic work by human agents, AI agents, or mixed teams.

The gates are a working hypothesis, not a fixed standard.

The goal is to find the smallest useful set of gates that reliably improves decisions and outcomes without unnecessary friction.

## Core validation question

Do these gates reliably identify when a team has sufficient evidence to proceed, and do they expose material conditions that would otherwise cause failure, rework, unnecessary risk, or poor outcomes?

## Validation dimensions

| Dimension | Question |
|---|---|
| Coverage | Do the gates cover important reasons work succeeds or fails? |
| Distinctness | Does each gate represent a materially different readiness question? |
| Necessity | Does each gate add information or control another gate does not? |
| Predictive value | Do gate decisions help predict later outcomes? |
| Actionability | Does a failed gate tell the team what needs to happen next? |
| Reliability | Can competent reviewers reach reasonably consistent decisions? |
| Economy | Is the benefit worth the effort required to evaluate the gates? |
| Generality | Does the model remain useful across work types and risk levels? |

## Evidence supporting the model

The model gains support when:

- most material readiness failures map naturally to an existing gate;
- each gate catches issues not adequately handled by another;
- work that passes the gates has better or more predictable outcomes;
- failed gates lead to useful corrective action;
- reviewers apply the gates consistently;
- low-risk work is not burdened with disproportionate controls;
- no significant independent readiness question repeatedly falls outside the model.

## Evidence against the model

Investigate the structure when:

- material failures repeatedly map to no existing gate;
- two gates consistently use the same evidence and fail for the same reason;
- one gate rarely changes a decision;
- work routinely passes all gates but fails for reasons the model should have anticipated;
- gate evaluation creates more friction than value;
- reviewers cannot distinguish gate boundaries reliably.

## False-confidence review

Critical case:

The work passed all required readiness gates, but a material problem occurred that a reasonable readiness process should have anticipated.

Classify the miss as:

- Criteria problem - the correct gate existed, but its criteria were incomplete.
- Evidence problem - the correct condition existed, but evidence was missing, stale, incomplete, misleading, or insufficiently verified.
- Decision problem - the criteria and evidence existed, but the readiness judgment was wrong.
- Model problem - no existing gate reasonably represents the missing readiness condition.

Do not add a new gate until repeated cases support a genuinely independent readiness question.

## False-block review

Also examine cases where a gate delayed or prevented work even though proceeding would have been reasonable.

Typical causes:

- evidence requirements disproportionate to risk;
- unnecessary escalation;
- duplicate checks;
- certainty required where explicit uncertainty would have been acceptable;
- low-risk work treated like high-risk work.

## Retrospective validation

Start with approximately 20-50 completed work items.

Include successes, failures, rework, abandoned work, unexpected escalations, and different risk levels.

For each case:

1. Reconstruct what was known before execution.
2. Evaluate each applicable gate using only evidence available at the time.
3. Record the gate decision.
4. Compare it with the actual outcome.
5. Identify failures, rework, surprises, and escalation.
6. Determine whether a gate should reasonably have caught them.
7. Record false blocks.

Do not grade historical readiness using hindsight evidence.

## Prospective validation

Apply the gates to approximately 10-20 live work items.

Before execution, record:

- gate decisions;
- evidence;
- assumptions and unknowns;
- conditions attached to READY WITH CONDITIONS;
- escalations and authority decisions.

After execution, record:

- actual outcome;
- rework and unexpected intervention;
- surprises;
- gate misses;
- false blocks;
- proposed improvements.

## Candidate metrics

Use as diagnostic signals, not targets:

- gate miss rate;
- false-block rate;
- unexpected escalation rate;
- rework after READY;
- READY WITH CONDITIONS success rate;
- gate intervention value;
- gate overlap rate;
- reviewer agreement;
- gate evaluation effort.

## Gate change rules

### Clarify a gate

When reviewers interpret it inconsistently or boundaries are unclear.

### Strengthen evidence requirements

When the same false-confidence failure recurs and the gate question is correct.

### Reduce evidence requirements

When false blocks are common or evidence does not affect decisions.

### Merge gates

When gates consistently use the same evidence, fail for the same reasons, and produce the same corrective actions.

### Split a gate

When one gate contains two independent readiness questions that lead to different actions or authorities.

### Add a gate

Only when:

1. multiple real cases expose the same gap;
2. the gap cannot reasonably fit existing gates;
3. the question is materially different;
4. detecting it earlier changes the decision;
5. the benefit outweighs added complexity.

### Retire a gate

When it rarely influences decisions and another gate fully covers its function.

## Initial validation plan

1. Retrospective: review 20-50 completed items.
2. Prospective: apply gates to 10-20 live items.
3. Review: analyze misses, false blocks, overlap, rework, escalation, and reviewer agreement.
4. Repeat: continue collecting evidence before structural changes.

## Working principle

Do not change the gate model because we can imagine a better structure. Change it when evidence from real work shows a meaningful blind spot, unnecessary duplication, or excessive friction.
