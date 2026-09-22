# Agentic Workspace Core

**Version:** 0.1  
**Status:** Proposed baseline

This package defines the smallest useful model for Agentic Workspaces, Capabilities,
and Capability Implementations.

## Purpose

Agentic Workspaces help humans and AI agents find the right context, understand their boundaries, use available capabilities, perform work, and return accepted results to authoritative locations.

Humans own intent, accountability, policy, and consequential decisions. Agents carry out work within explicit authority.

## Read This Package

1. [Core Model](01-core-model.md) — the concepts and how they relate.
2. [Workspace](02-workspace.md) — the workspace and its kernel.
3. [Capabilities](03-capabilities.md) — six Capabilities, their contracts, and Capability Implementations.
4. [Workflows and Runs](08-workflows-and-runs.md) — reusable workflow contracts, stages, isolated runs, acceptance, and ICM mapping.
5. [Workspace Conventions](04-workspace-conventions.md) — rules every workspace follows.
6. [Capability Conventions](05-capability-conventions.md) — rules for Capabilities and Capability Implementations.
7. [General Rules](06-general-rules.md) — rules that apply across the model.
8. [Workspace Interface](07-workspace-interface.md) — the public boundary contract for workspace-to-workspace interaction.
9. [Reference Scaffold](examples/reference-scaffold.md) — a small filesystem-backed example.

## Guiding Statement

> The kernel defines the environment. Capabilities define bounded functions. Capability Implementations realize them. Bindings connect requirements to implementations. Workflows compose them. Runs perform the work. Acceptance and promotion make results authoritative.

## Scope

This package defines the conceptual model and its conventions. Detailed schemas, runtime integrations, folder scaffolds, and domain-specific workflows may implement this model but must not redefine it.
