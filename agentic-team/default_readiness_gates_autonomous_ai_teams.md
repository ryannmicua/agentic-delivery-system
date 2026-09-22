# Default Readiness Gates for Agentic Teams

## Status

Working draft for refinement.

## Purpose

This document defines a default set of readiness gates for work performed by human agents, AI agents, or mixed teams.

The gates answer:

What must be true before the team is ready to move forward?

They are defaults, not rigid stage gates. Evidence requirements should vary with risk, uncertainty, reversibility, and consequence.

The goal is not certainty. The goal is sufficient readiness to proceed responsibly.

## Operating model

### Context of the Real World

Question: What is actually true right now?

### Problem Space

Question: What needs to change, and why?

### Capability

Question: What ability do we have or need to cause the desired change?

Capability is relative to the problem. Possessing a tool, model, or skill does not by itself mean the required capability exists.

## Readiness principles

1. Readiness is not certainty.
2. Evidence should be proportional to risk.
3. Unknowns must be visible.
4. A failed gate creates explicit work.
5. Gates support appropriate autonomy rather than maximum autonomy.
6. The team must be able to stop, escalate, or reframe.
7. Gate decisions may become stale when evidence or reality changes.

## Gate 1 - Context Ready

### Core question

Do we understand reality well enough to define and reason about the problem without a material context gap invalidating the work?

### Default criteria

- relevant current-state facts are understood;
- important stakeholders and affected parties are identified;
- relevant systems, processes, policies, and dependencies are known;
- important constraints and risks are identified;
- relevant data and sources of truth are known or accessible;
- material historical decisions are understood where relevant;
- assumptions are distinguished from verified facts;
- material unknowns are explicit;
- no unresolved context gap is likely to invalidate the next stage.

### If not ready

Gather context, involve missing stakeholders, inspect relevant systems or data, verify assumptions, or stop if sufficient context cannot reasonably be established.

## Gate 2 - Problem Ready

### Core question

Is the problem defined well enough that we can reason about required outcomes without prematurely committing to a solution?

### Default criteria

- the problem or opportunity can be clearly stated;
- affected users, stakeholders, or systems are understood;
- the desired outcome is explicit;
- the value of solving the problem is understood;
- scope and non-goals are sufficiently clear;
- important constraints are known;
- success can be evaluated;
- material assumptions and risks are visible;
- important trade-offs are understood;
- the problem statement is not merely a disguised solution request unless that solution is an explicit constraint.

### If not ready

Clarify intent, investigate the problem, separate symptoms from causes, establish success criteria, narrow or split scope, or return to Context Discovery.

## Gate 3 - Capability Ready

### Core question

Do we have or can we assemble the capability required to produce the desired outcome?

### Default criteria

- required capabilities are identified;
- existing capabilities are matched against requirements;
- capability gaps are explicit;
- required humans, AI agents, tools, skills, knowledge, data, APIs, workflows, infrastructure, and resources are available or obtainable;
- required access and permissions are understood;
- capability limitations are known where material;
- the capability combination can operate within relevant constraints;
- dependencies between capabilities are understood;
- remaining non-blocking gaps have a reasonable path to resolution.

### Capability analysis questions

1. What ability is required?
2. Do we already have it?
3. Who or what provides it?
4. How proven or reliable is it for this type of work?
5. What inputs or permissions does it require?
6. What limitations apply?
7. Does it need to be combined with another capability?
8. What happens if it fails?
9. Is human or specialist judgment required?
10. What is still missing?

## Gate 4 - Execution Ready

### Core question

Are the solution approach, responsibilities, authority, guardrails, and validation sufficient to begin execution?

### Default criteria

- an actionable approach exists;
- required capabilities are assigned or composed;
- responsibilities and ownership are clear;
- required inputs and dependencies are available;
- required access, permissions, and approvals are in place;
- authority and autonomy boundaries are explicit;
- guardrails and prohibited actions are clear where needed;
- stop and escalation conditions are defined for material risks;
- significant risks are acceptable;
- expected outputs are clear;
- validation is defined before execution;
- evidence to capture during execution is known;
- irreversible or high-impact actions have the required control.

## Gate 5 - Outcome Ready

### Core question

Do we have sufficient evidence that the work produced the intended change, and have we captured what reality now looks like?

### Default criteria

- planned execution completed or a deliberate stop decision was made;
- required outputs exist;
- acceptance criteria were evaluated;
- tests, checks, or evals passed or exceptions are understood;
- the intended real-world outcome was measured or observed where practical;
- unintended effects and residual risks are understood;
- material deviations are recorded;
- follow-up work is identified where needed;
- relevant context is updated;
- reusable capability learning is captured;
- useful failures, patterns, and lessons are recorded;
- there is enough evidence to close, continue, correct, revert, or reframe.

## Gate decision states

### READY

Sufficient evidence exists to proceed at the proposed level of risk and authority.

### READY WITH CONDITIONS

The team may proceed if named assumptions, safeguards, monitoring, approvals, or follow-up actions remain in force.

### NOT READY

A material gap prevents responsible progression.

### ESCALATE

The team cannot make the decision within its authority, competence, available evidence, or risk tolerance.

### STOP

The work should not continue under the current intent, context, problem definition, capability, or risk conditions.

## Risk-based tailoring

Low-risk, reversible work should use lighter evidence and may evaluate multiple gates together.

Moderate-risk work should use explicit evidence and stronger review.

High-risk or difficult-to-reverse work should use stronger source verification, explicit authority, stricter capability validation, stronger guardrails, and recovery planning.

## Working definition

The default readiness model consists of five gates:

1. Context Ready
2. Problem Ready
3. Capability Ready
4. Execution Ready
5. Outcome Ready

Proceed when the evidence is sufficient for the risk, not when uncertainty has disappeared.
