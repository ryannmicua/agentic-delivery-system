# Evidence Model for Agentic Work

## Status

Working draft for refinement.

## Purpose

This model defines how human agents, AI agents, and mixed teams should use evidence when making decisions, evaluating readiness, executing work, and determining outcomes.

It answers:

What gives us enough reason to believe something is true, and when is that evidence sufficient to act?

The goal is not to eliminate uncertainty. The goal is to make uncertainty, assumptions, evidence quality, and decision confidence explicit enough to proceed responsibly.

## Core principle

For any material claim, ask:

1. What exactly are we claiming?
2. What evidence supports it?
3. Where did the evidence come from?
4. How current is it?
5. How reliable and applicable is it?
6. What contradicts it?
7. What remains unknown?
8. Is the evidence sufficient for the decision we are about to make?

Confidence is not evidence. Authority is not evidence. Fluency is not evidence. Evidence is evidence.

## Agent-neutral evidence

The same standards apply whether evidence or judgment comes from:

- a human agent;
- an AI agent;
- an automated system;
- a mixed team.

An assertion does not become fact solely because of who or what produced it.

## Evidence chain

```text
Reality
   |
Observation / Source
   |
Evidence
   |
Claim
   |
Assessment
   |
Decision
   |
Action
   |
Observed Outcome
   |
New Evidence
```

## Core definitions

### Claim

A statement that may influence a decision.

### Evidence

Information that supports or contradicts a claim.

### Source

Where the evidence originated.

### Provenance

Where evidence came from, who or what produced it, when it was produced, how it was obtained, and how it was transformed.

### Observation

Something directly detected or recorded.

### Interpretation

Meaning assigned to observations.

### Inference

A conclusion derived from evidence.

### Assumption

Something temporarily accepted without sufficient evidence.

### Decision

A choice made using claims, evidence, uncertainty, authority, and risk.

## Evidence types

- Direct observation
- System-generated evidence: logs, telemetry, records, audit trails
- Documentary evidence: policies, specifications, procedures, tickets, reports
- Test or experimental evidence: tests, prototypes, benchmarks, simulations, evals
- Human testimony or judgment
- AI-generated analysis or judgment
- Historical evidence
- External evidence: standards, research, vendor documentation, regulatory guidance

No type is universally superior. Suitability depends on the claim.

## Evidence quality dimensions

Assess evidence using:

- relevance;
- reliability;
- provenance;
- freshness;
- specificity;
- independence;
- completeness;
- integrity;
- reproducibility;
- applicability.

These are a vocabulary for judgment, not a mandatory numerical score.

## Evidence quality states

- STRONG - directly relevant, reliable, current, and appropriate; material contradictions addressed.
- ADEQUATE - limitations exist but are understood and acceptable for the decision.
- WEAK - some support exists, but material limitations remain.
- UNKNOWN - quality, provenance, or applicability has not been adequately established.

## Claim states

- VERIFIED
- SUPPORTED
- PLAUSIBLE
- ASSUMED
- CONTESTED
- CONTRADICTED
- UNKNOWN
- STALE

## Evidence versus confidence

Confidence is how strongly an agent believes a conclusion. Evidence is what supports the conclusion. Keep them separate.

## Evidence sufficiency

Evidence needs to be sufficient for the decision, not perfect.

Require stronger evidence as these increase:

- consequence;
- irreversibility;
- uncertainty;
- novelty;
- blast radius;
- sensitivity;
- cost of failure;
- difficulty detecting failure afterward.

Evidence burden may decrease when work is:

- low consequence;
- easily reversible;
- isolated;
- well understood;
- strongly monitored;
- inexpensive to correct;
- experimentally bounded.

The burden of evidence should be proportional to the consequence of being wrong.

## Decision thresholds

### Low evidence threshold

Suitable for low-consequence, reversible, small-blast-radius work.

### Moderate evidence threshold

Suitable for normal operational or delivery work with meaningful consequences.

### High evidence threshold

Suitable where consequences are significant or difficult to reverse. Expect stronger provenance, authoritative or direct sources where available, independent verification, explicit treatment of contradictions, stronger capability validation, and appropriate human or specialist judgment.

## Triangulation

Important claims should use different evidence perspectives when warranted. Multiple summaries from the same original source do not count as independent confirmation.

## Contradictory evidence

Preserve and investigate conflicts rather than silently averaging or discarding them.

Record:

- conflicting claims;
- supporting sources;
- evidence quality;
- possible reasons for disagreement;
- whether the disagreement matters to the decision.

## Evidence freshness

Evidence can expire.

Readiness may become:

STALE - RE-EVALUATION REQUIRED

Re-evaluate when material supporting evidence changes, expires, or becomes unreliable.

## Derived evidence and transformation

Evidence is often transformed through queries, spreadsheets, analysis, summaries, and briefings. Each transformation can introduce selection bias, calculation error, loss of detail, or interpretation. Preserve enough provenance to trace important conclusions toward the underlying source.

## Negative evidence

Absence of evidence is not automatically evidence of absence. Claims should not exceed what the evidence supports.

## Evidence and the five readiness gates

### Context Ready

Evidence supports claims about current reality.

### Problem Ready

Evidence supports claims about the problem, affected parties, causes, desired outcomes, impact, and success conditions.

### Capability Ready

Evidence supports claims that a human, AI, tool, workflow, or team can perform the required work under relevant conditions.

### Execution Ready

Evidence supports claims that the approach is feasible, dependencies and authority exist, controls are active, risks are understood, and validation and recovery are sufficient.

### Outcome Ready

Evidence supports claims about what was done, what changed, whether success criteria were met, unintended effects, residual risks, and real-world outcomes.

## Minimum evidence record

For material evidence, capture:

- Claim
- Claim State
- Evidence
- Source
- Evidence Type
- Provenance
- Observed / Produced date or period
- Evidence Quality
- Material Limitations
- Contradictory Evidence
- Material Unknowns
- Decision Supported
- Evidence Threshold
- Re-evaluation Trigger

Do not require this for every trivial fact.

## Evidence ownership

Where practical, evidence should have a responsible source or owner that produces it, maintains it, corrects it, and indicates when it becomes stale.

## Evidence access

Evidence access should respect privacy, security, confidentiality, need-to-know, regulation, and system permissions. If an agent is reasoning from a derived or restricted view rather than raw evidence, that limitation should remain visible.

## Initial operating rules

1. Material claims should be supported by identifiable evidence.
2. Separate observation, interpretation, inference, and assumption.
3. Preserve provenance for evidence that affects important decisions.
4. Evaluate evidence for relevance, reliability, freshness, and applicability.
5. Treat human and AI assertions as claims, not facts by default.
6. Do not treat dependent sources as independent confirmation.
7. Make contradictory evidence and material unknowns visible.
8. Increase the burden of evidence as consequence and irreversibility increase.
9. Allow readiness evidence to become stale when reality changes.
10. Compare pre-action evidence with actual outcomes so the evidence system can learn.

## Working definition

Evidence is traceable information that increases or decreases our basis for believing a claim relevant to a decision.

Evidence quality describes how much that information should be trusted for that claim.

Evidence sufficiency describes whether the available body of evidence is good enough for the decision and risk involved.

Confidence describes how strongly an agent believes a conclusion.
