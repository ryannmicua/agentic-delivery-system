# Workspace

A workspace is an environment organized around a coherent purpose. It brings
together routes to context, available capabilities, and places to perform and
retain work.

It may be implemented in a repository, shared folder, document system, application,
or a combination of systems. Physical containment is optional: a workspace can
reference a source without copying it locally.

## The entry point

Every workspace needs one discoverable entry point that answers:

| Question | What to provide |
|---|---|
| What is this for? | Purpose and scope, including significant exclusions. |
| Where should I look? | Task-oriented routes to relevant context. |
| What can help me do the work? | Available tools, skills, services, or people, with usage instructions or links. |
| How do I start? | How requests arrive and links to any reusable procedures or workflows. |
| Where does work go? | Where ongoing work and final results belong. |
| What constraints matter? | Actual restrictions, decisions requiring another person, or known limitations relevant here. |

These answers can fit in one document. Link to existing instructions rather than
reproducing them. If there is no special local constraint or reusable procedure, say so
briefly rather than inventing one.

Use the entry mechanism actors already encounter, such as a repository README,
an agent instruction file, or a shared landing page. If humans and different agent
runtimes use different entry files, have those files point to the same shared
content. Ensure the runtime actually loads or routes to that content.

## Scope and composition

Keep one workspace until distinct purposes or substantially different context
routes make separation useful. A folder for a topic does not automatically need
to become a workspace.

Related workspaces can reference shared documents, tools, procedures, and workflows directly
where existing access permits. No workspace-specific interface protocol is
required. State which shared instructions apply; directory nesting alone should
not be relied on to establish inheritance across different runtimes.

A local workspace can specialize shared defaults. Its entry point links to the
shared source and describes the local differences. See [context resolution](02-context.md)
for how those differences apply.

## Keeping it useful

Update routes when sources move, tools change, or repeated tasks reveal missing
instructions. Keep durable knowledge at its relevant source and link to it from
the workspace. Fix misleading routes when discovered; a scheduled maintenance
process is unnecessary unless experience demonstrates a need.
