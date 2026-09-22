# Session Summary: Operating Model for Agentic Teams

## Session focus

We developed a working operating model for teams made up of human agents, AI agents, or mixed human-AI teams.

The model starts with three domains:

1. Context of the Real World
2. Problem Space
3. Capability

The goal is to make this model operational rather than conceptual.

## Core model

### Context of the Real World

Question: What is actually true right now?

This includes people, stakeholders, processes, systems, policies, data, constraints, dependencies, history, and current conditions.

### Problem Space

Question: What needs to change, and why?

This includes problems, opportunities, desired outcomes, affected users, value, scope, non-goals, risks, assumptions, trade-offs, and success criteria.

### Capability

Question: What ability do we have or need to cause the desired change?

Capability is the ability to solve a problem or produce a desired outcome. It may come from humans, AI agents, skills, tools, APIs, software, data, workflows, permissions, infrastructure, or combinations of these.

Capability is not the solution. A solution is the deliberate application or composition of capability to a problem within the real-world context.

## Agent-neutral principle

Everything in this operating model should apply to:

- human agents;
- AI agents;
- mixed human-AI teams.

The model should describe what must be true for work to proceed, not assumptions about whether the actor is human or AI.

## Default lifecycle

```text
Intent / Trigger
      |
Context Discovery
      |
[ CONTEXT READY? ]
      |
Problem Framing
      |
[ PROBLEM READY? ]
      |
Capability Analysis & Composition
      |
[ CAPABILITY READY? ]
      |
Planning / Authorization
      |
[ EXECUTION READY? ]
      |
Execute
      |
Evaluate
      |
[ OUTCOME READY? ]
      |
Close / Learn / Update Reality
      ^
      +---------------------------
```

This is a controlled loop rather than a one-way pipeline. New evidence may invalidate an earlier readiness decision and send work back to a previous stage.

## Five default readiness gates

1. Context Ready - We understand reality well enough to reason about the problem.
2. Problem Ready - We understand what needs to change and what outcome matters.
3. Capability Ready - We have or can assemble the ability required to cause that change.
4. Execution Ready - The approach, authority, responsibilities, controls, and validation are sufficient to act.
5. Outcome Ready - We have enough evidence to determine what changed, whether the intended outcome was achieved, and what should happen next.

Gate states:

- READY
- READY WITH CONDITIONS
- NOT READY
- ESCALATE
- STOP

A gate does not require certainty. It requires that uncertainty is understood well enough to proceed safely for the risk involved.

## Validating the five gates

The five gates are a working hypothesis.

The right model should be the smallest set of gates that:

- covers materially different reasons work should not proceed;
- avoids unnecessary duplication;
- predicts or prevents meaningful failures;
- produces useful corrective action;
- can be applied consistently;
- remains proportional to risk and work size.

Validation dimensions:

- Coverage
- Distinctness
- Necessity
- Predictive value
- Actionability
- Reliability
- Economy
- Generality

Initial validation approach:

1. Retrospective validation against roughly 20-50 completed work items.
2. Prospective validation against roughly 10-20 live work items.
3. Record gate decisions before execution.
4. Compare those decisions with actual outcomes.
5. Track gate misses and unnecessary blocks.
6. Change the model only when recurring evidence supports a structural change.

## Readiness failure taxonomy

The taxonomy is deliberately independent of the five gates so validation does not become circular.

Initial failure classes:

- F1 - Reality Misunderstood
- F2 - Problem Misframed
- F3 - Success Definition Inadequate
- F4 - Scope or Boundary Failure
- F5 - Capability Gap
- F6 - Capability Misjudged
- F7 - Access or Authority Failure
- F8 - Plan or Coordination Failure
- F9 - Control or Guardrail Failure
- F10 - Validation Failure
- F11 - Outcome Failure
- F12 - Unintended Consequence
- F13 - Environmental Change
- F14 - Human or Agent Execution Error
- F15 - Unknown / Unclassified

The validation discipline is:

Observe -> Classify -> Analyze -> Accumulate Evidence -> Change the Model

## Evidence model

The evidence model sits underneath all five gates.

Central question:

What gives us enough reason to believe something is true, and when is that evidence sufficient to act?

Core principles:

- confidence is not evidence;
- authority is not evidence;
- human and AI assertions are both claims that require appropriate support;
- observation, interpretation, inference, and assumption should remain distinct;
- material evidence should have traceable provenance;
- evidence freshness matters;
- contradictory evidence should remain visible;
- evidence requirements should increase with consequence and irreversibility;
- evidence can become stale and force readiness re-evaluation;
- actual outcomes should be compared with pre-action evidence so the model can learn.

## Other operating-system components identified

These are not additional gates by default. They are mechanisms that make the gates trustworthy and operable.

1. Work Intake and Triage
2. Decision Rights and Authority
3. State and Transition Rules
4. Evidence Freshness / Context Drift
5. Capability Registry and Capability Evidence
6. Resource and Priority Conflict Handling
7. Economics and Proportionality
8. Observability
9. Learning Promotion Rules

## Action steps

1. Refine the five readiness gates using evidence from real work.
2. Define Decision Rights and Authority.
3. Define State and Transition Rules.
4. Design the Capability Registry.
5. Define Work Intake and Triage.
6. Run retrospective validation against 20-50 past work items.
7. Run a prospective pilot against 10-20 live work items.
8. Review repeated misses, false blocks, overlap, disagreement, unclassified failures, escalation, and stale evidence before changing the gate structure.

## Working principle

Domains tell the team what kind of truth it needs. Readiness gates determine whether that truth is sufficient. The lifecycle determines what happens next.
