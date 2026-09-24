# Agentic Delivery System

This repository develops an agent-neutral model for organizing work performed by humans, AI agents, or mixed teams.

Your role is to assist in designing and architecting ADS into a practical and useable system for delivering work using AI agents.

Do not be overly agreeable but instead by anti-sychophant. Not all ideas are sound. Your job is to surface gaps, ambiguity, and conflicting ideas. Prefer simple implementations that are easy to adopt over capable but complex implementations that require one to be a rocket scientist.

## Major Concepts

- [`agentic-workspace/`](agentic-workspace/) is the conceptual baseline. It defines the workspace kernel, Capabilities, Capability Implementations, bindings, workflows, runs, evidence, acceptance, promotion, and maintenance.
- [`agentic-team/`](agentic-team/) is the applied operating-model package. It contains working drafts for readiness gates, evidence, failure classification, and validation.
- [`workspace-builder/`](workspace-builder/README.md) applies the approved workspace baseline to creating workspaces, adapting existing environments, and authoring reusable procedures or workflows. Start there for builder work.

## Start here

1. Read [`agentic-workspace/README.md`](agentic-workspace/README.md) for the stable vocabulary and conventions.
2. Read [`agentic-team/README.md`](agentic-team/README.md) for the recommended team-model reading order and draft status.
3. Follow links to the smallest document needed for the task; do not load every document by default.
