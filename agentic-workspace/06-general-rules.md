# General Rules

These rules apply across workspaces, Capabilities, Capability Implementations,
workflows, runs, and maintenance.

1. **Keep one authoritative home.**  
   Store each durable rule, fact, definition, and decision in one place. Reference it elsewhere.

2. **Standardize interfaces, not directory trees.**  
   Require the information and behavior the system needs. Allow projects to bind those concepts to suitable locations.

3. **Separate capability from authority.**  
   Having a component or tool does not grant permission to use it.

4. **Keep definitions separate from execution.**  
   Kernels, Capability contracts, Capability Implementation profiles, and workflows
   describe reusable behavior. Runs record request-specific work.

5. **Do not rely on hidden conversation.**  
   Record or reference every material input, assumption, decision, and handoff.

6. **Treat working output as untrusted.**  
   Agent-created material remains working state until evidence supports acceptance and authorized promotion.

7. **Separate completion, acceptance, and promotion.**  
   Finishing work does not automatically make its result accepted or authoritative.

8. **Exchange information through public interfaces.**  
   Workspaces must not read another workspace's private context, files, bindings,
   working artifacts, drafts, or run state directly. They exchange information only
   through a versioned public interface, published context, accepted artifact, or
   explicit handoff. A public interface may expose in-progress status, results,
   failures, evidence summaries, and accepted artifacts without exposing private run
   state.

9. **Keep local extensions private by default.**  
   Child workspaces may introduce new context sources, Capabilities, Capability
   Implementations, bindings, and workflows. These remain local and private unless
   explicitly exposed through a public interface.

10. **Let authority and accepted results cross governed boundaries.**  
    Parents may provide shared direction and authority through declared contracts and
    public interfaces. Children return accepted artifacts and reusable learning
    through those interfaces to the lowest common level where they apply.

11. **Use the same core documents for humans and agents.**  
    Runtime-specific files may point to the core model but cannot redefine capability
    contracts, policy, or authority.

12. **Make consequential actions traceable.**  
    Preserve sources, versions, evidence, decisions, and responsible authority.

13. **Make change inexpensive and explicit.**  
    Prefer readable, portable, versioned contracts. Add infrastructure only when observed needs justify it.
