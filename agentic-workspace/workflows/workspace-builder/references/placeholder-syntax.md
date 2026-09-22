# Workspace Builder Placeholder Syntax

Generated workspace templates may use placeholders for installation-specific values.
The syntax is deliberately small so validation can check it without a special parser.

## Value placeholders

Use `{{NAME}}` for a required value supplied during setup or a run. Names use uppercase
letters, digits, and underscores, for example `{{WORKSPACE_NAME}}` or
`{{PRIMARY_AUDIENCE}}`.

Every value placeholder must:

- be listed in the generated setup questionnaire;
- identify the file or files where the answer is used;
- have one owner and one authoritative home; and
- define what happens when the answer is missing.

## Conditional sections

Use a complete-section block when a stage or feature is optional:

```text
{{?OPTIONAL_STAGE}}
## Optional Stage

This entire section is included only when the owner enables the stage.
{{/OPTIONAL_STAGE}}
```

The opening and closing markers must wrap a complete heading and its content. Do not
wrap a sentence, table row, list item, or part of a heading. A conditional section
must have a corresponding setup question or a declared default.

## Validation rules

- No unresolved placeholder may remain in an accepted scaffold.
- Every questionnaire variable must map to at least one placeholder or an explicitly recorded decision.
- Placeholder syntax must not be used to bypass authority, acceptance, promotion, or interface rules.
- A run may resolve values in its context manifest, but the reusable workflow definition must keep them symbolic.
