# Stage 02: Mapping

Turn the discovery map into formal stage contracts and verify the dependency graph.

## Inputs

| Source | Scope | Why |
|---|---|---|
| `artifacts/01-discovery/workflow-map.md` | Full file | The workflow to formalize |
| `references/conventions-reference.md` | ADS workflow, run, capability, and authority rules | Write contracts that fit the model |
| `../../../08-workflows-and-runs.md` | Workflow and run sections | Pin acceptance and transition expectations |

## Process

1. Read the discovery map and list every proposed stage in order.
2. Write each stage's Inputs, Process, Outputs, authority, completion, evidence, and failure behavior.
3. Map which stages read from which prior artifacts and identify the owner of each durable fact.
4. Declare required Capabilities and the binding information the workspace must resolve.
5. Define workflow acceptance measures and the evidence each measure requires.
6. Define transitions for pass, fail, missing, stale, inconclusive, retry, return, stop, and escalation.
7. Draw the dependency graph and verify it is one-way and acyclic.
8. Verify every output is consumed by a downstream stage, final acceptance, or promotion.
9. Present the dependency diagram and contracts to the owner; revise after the checkpoint.
10. Apply the audit below and write the contracts artifact.

## Checkpoint

| Agent presents | Owner decides |
|---|---|
| Dependency diagram, formal contracts, required Capabilities, acceptance measures, and transition rules | Whether the flow, contracts, and authority boundaries are correct |

## Audit

| Check | Pass condition |
|---|---|
| No circular references | The dependency graph is directed and acyclic |
| Output consumption | Every output has a declared consumer or is a final accepted result |
| Contract completeness | Every stage has non-empty Inputs, Process, Outputs, completion, and failure behavior |
| Canonical sources | No durable fact has more than one authoritative home |
| Authority fit | No stage grants itself access, acceptance, or promotion authority |
| Acceptance traceability | Every measure names the evidence and evaluator needed to assess it |

## Output

Write `runs/<run-id>/artifacts/02-mapping/stage-contracts.md` with the formal contracts,
ASCII or Mermaid dependency diagram, canonical-source map, Capability requirements,
acceptance measures, transition policy, checkpoint decision, and audit evidence.
