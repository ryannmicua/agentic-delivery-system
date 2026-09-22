# Stage 05: Validation

Verify the candidate workspace, questionnaire, contracts, and cross-references before
the result can be accepted or promoted.

## Inputs

| Source | Scope | Why |
|---|---|---|
| `artifacts/03-scaffolding/workspace-scaffold/` | Entire candidate workspace | The workspace being validated |
| `artifacts/04-questionnaire-design/questionnaire.md` | Full file and coverage matrix | Verify setup coverage |
| `artifacts/02-mapping/stage-contracts.md` | Contracts and dependency graph | Verify the candidate realizes the design |
| `references/conventions-reference.md` | Full file | Validate against ADS conventions |
| `references/placeholder-syntax.md` | Full file | Validate placeholders and conditional sections |

## Process

Run each check, recording pass/fail, evidence, issues, and fixes. Fix the candidate
artifact in the run and rerun failed checks before writing the final report.

1. **Cross-reference integrity:** every candidate path and public reference resolves to a real declared file, interface, or published source.
2. **Dependency integrity:** the stage and reference graph is directed and acyclic.
3. **Placeholder coverage:** every placeholder has a questionnaire question or fixed default, and every question has a mapped effect.
4. **Conditional validity:** every conditional block wraps a complete section and has a selector and disabled behavior.
5. **Stage handoff chain:** each stage output is available at the location consumed by the next stage or by acceptance.
6. **Definition purity:** reusable definitions contain no request-specific run output, hidden transcript, or mutable status.
7. **Kernel completeness:** purpose, boundary, owner, context, authority, Capabilities, bindings, workflows, interfaces, state, acceptance, promotion, and maintenance are present where applicable.
8. **Checkpoint and audit coverage:** creative or build stages have a checkpoint or explicit reason to omit one, and build stages have specific audit pass conditions.
9. **Contract purity:** specifications state what and when; implementation-specific details are kept in implementation profiles or build stages.
10. **Run isolation:** the candidate does not write to an authoritative destination before promotion, and the run retains the evidence needed to explain its result.
11. **Naming and portability:** names are lowercase-with-hyphens where the filesystem binding requires them, stage folders are zero-padded, and required empty roots are represented explicitly.
12. **Prerequisite coverage:** each declared tool has an owner, setup or verification path, and required/optional status.
13. **Quality scan:** formatting is valid, jargon is explained, and no unresolved authority or acceptance ambiguity is hidden in prose.

## Output

Write `runs/<run-id>/artifacts/05-validation/validation-report.md` with the checklist,
evidence, issues found, fixes applied, remaining exceptions, and an explicit
`acceptance_recommendation` of `pass`, `fail`, or `inconclusive`. A `pass` is a
recommendation only; acceptance and promotion remain separate governed events.
