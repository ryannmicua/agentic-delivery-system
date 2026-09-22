# Readiness Failure Taxonomy

## Status

Working draft for validation of the agentic readiness model.

## Purpose

This taxonomy provides a consistent way to classify failures, rework, escalations, and unexpected outcomes during work performed by human agents, AI agents, or mixed teams.

The taxonomy is intentionally independent of the five readiness gates.

First classify what actually went wrong. Only then ask which readiness gate, if any, should have caught it.

## Classification flow

```text
Observed Failure
      |
Failure Type
      |
Underlying Cause
      |
Readiness Analysis
      |
Should a gate have caught this?
      |
Criteria / Evidence / Decision / Model problem
```

## Failure types

| Code | Failure Type | Diagnostic question |
|---|---|---|
| F1 | Reality Misunderstood | Was our understanding of the current state materially wrong or incomplete? |
| F2 | Problem Misframed | Were we solving the wrong problem or pursuing the wrong change? |
| F3 | Success Definition Inadequate | Did we know what a good outcome needed to look like? |
| F4 | Scope or Boundary Failure | Were the boundaries of the work wrong, missing, or misunderstood? |
| F5 | Capability Gap | Did successful execution require an ability we did not actually have? |
| F6 | Capability Misjudged | Did we overestimate how well an available capability could perform this work? |
| F7 | Access or Authority Failure | Could we perform the work, but not legitimately or technically exercise that capability? |
| F8 | Plan or Coordination Failure | Did we have what we needed but organize or apply it incorrectly? |
| F9 | Control or Guardrail Failure | Did we fail to constrain, stop, contain, or recover from execution appropriately? |
| F10 | Validation Failure | Did our validation fail to detect that the work was wrong or incomplete? |
| F11 | Outcome Failure | Did we execute correctly but fail to achieve the intended outcome? |
| F12 | Unintended Consequence | Did the intervention create a material effect we failed to anticipate? |
| F13 | Environmental Change | Did reality change enough that previously valid readiness evidence became invalid? |
| F14 | Human or Agent Execution Error | Was this principally an execution mistake rather than a readiness defect? |
| F15 | Unknown / Unclassified | Do we understand the failure well enough to classify it without forcing it? |

## Cross-cutting cause tags

- Missing information
- Incorrect information
- Stale information
- Unverified assumption
- Ambiguity
- Missing stakeholder
- Missing dependency
- Capability absent
- Capability unreliable
- Access unavailable
- Authority unavailable
- Poor handoff
- Coordination error
- Scope drift
- Guardrail absent
- Guardrail ineffective
- Validation absent
- Validation weak
- Environment changed
- Human error
- Agent error
- Novel condition

## Consequence classification

- C0 - No Material Impact: caught before meaningful impact.
- C1 - Minor Rework: small correction.
- C2 - Material Rework or Delay: meaningful additional effort or delay.
- C3 - Significant Operational Impact: users, systems, cost, or delivery materially affected.
- C4 - High-Consequence Event: security, privacy, safety, compliance, financial loss, irreversible damage, or similarly serious consequence.

## Detection point

Record when the problem became visible:

- During Context Discovery
- During Problem Framing
- During Capability Analysis
- During Planning
- Before Execution
- During Execution
- During Validation
- After Release / Deployment
- During Outcome Evaluation
- Later / External Discovery

## Readiness mapping

Only after classification:

1. Should readiness have caught it? Yes / No / Unclear
2. Which gate should have caught it? Context / Problem / Capability / Execution / Outcome / No existing gate / Unclear
3. Why did it miss? Criteria / Evidence / Decision / Model

## Working discipline

Observe -> Classify -> Analyze -> Accumulate Evidence -> Change the Model

Do not change the taxonomy simply to preserve the five-gate model, and do not change the five-gate model simply because one new failure appears.
