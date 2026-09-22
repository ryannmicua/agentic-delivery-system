# Stage 04: Questionnaire Design

Design the setup questionnaire that a future owner will use to instantiate the
generated workspace. This questionnaire belongs to the candidate workspace; it is
different from the builder's own intake questionnaire.

## Inputs

| Source | Scope | Why |
|---|---|---|
| `artifacts/01-discovery/workflow-map.md` | Variables, optional paths, tools, actors, and decisions | Preserve domain-specific setup needs |
| `artifacts/03-scaffolding/workspace-scaffold/` | Full candidate tree | Derive questions from actual placeholders and declared configuration |
| `references/placeholder-syntax.md` | Full file | Enforce variable and conditional-section rules |
| `setup/questionnaire.md` | Question design patterns | Reuse useful coverage without copying builder-only questions blindly |

## Process

1. Scan the candidate for value placeholders, conditional sections, tool choices, authority decisions, interface consumers, and promotion destinations.
2. Write one clear question for each required setup value and decision, with a stable identifier and answer format.
3. Add questions for optional stages, optional tools, ownership, maintenance, and acceptance when the candidate declares them.
4. Map every question to the candidate file or files it configures and identify the authoritative home of its answer.
5. Add guidance for unknown answers, defaults, and decisions that must stop setup.
6. Present the draft questionnaire and coverage matrix to the owner for review.
7. Apply the audit below, revise failures, and write the questionnaire artifact.

## Checkpoint

| Agent presents | Owner decides |
|---|---|
| Questionnaire, variable-to-file coverage matrix, optional-path questions, and authority questions | Whether a future owner can configure the workspace without hidden assumptions |

## Audit

| Check | Pass condition |
|---|---|
| Placeholder coverage | Every candidate placeholder has exactly one question or an explicit fixed default |
| Question coverage | Every question changes a candidate value, enables a declared branch, or records a required decision |
| Authority coverage | Ownership, allowed actions, acceptance, promotion, and maintenance are asked when applicable |
| Conditional coverage | Optional stages and tools have a selector and a defined disabled behavior |
| Answer usability | Questions state the expected format and what an unknown answer does |

## Output

Write `runs/<run-id>/artifacts/04-questionnaire-design/questionnaire.md` and a coverage
matrix beside it. Promotion must include the accepted questionnaire in the candidate
workspace's setup location.
