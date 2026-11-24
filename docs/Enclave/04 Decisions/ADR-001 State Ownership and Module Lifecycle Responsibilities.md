**Date:** 2026-11-24

This is Enclave's current architectural plan, not a proposal. It establishes responsibilities and required behavior; implementation mechanisms remain undecided. Future changes should explicitly revise or supersede this decision.

## Context

Enclave hosts modules with different state and activity requirements. Layout switching must preserve the user's working state and required activity without requiring every remembered instance to remain running. A module definition, running instance, window, and saved resource are distinct concepts with potentially different lifetimes.
## Decision

### Ownership

- **Enclave** owns workspace state: instance tracking, window position, size and visibility, layout membership, and coordination of creation, closure, and restoration.
- Enclave is the **single source of truth** for window and instance lifecycle state. Modules may request changes; Enclave determines the transition, and modules respond with their specialized behavior.
- **Modules** own their specialized state and behavior, including what must be preserved. Enclave remembers enough information to request restoration without interpreting module content.
- Instance limits and background requirements are separate module characteristics, expressed through a shared host contract rather than module-specific handling in Enclave. The programming interfaces are not yet defined.

### Instances and Layouts

- Single-instance modules can share one instance across layouts. Multi-instance modules use separate instances in different layouts; those instances may display the same saved resource.
- Layout switching preserves the user's working state. Modules declare whether they require continued activity while hidden. Other instances may be retained or ended and restored, provided their required state survives. The retention policy remains undecided.
- Creating a fresh instance and restoring a remembered instance are distinct operations.
- Explicitly closing a window removes it from the current layout. References in other layouts preserve its remembered identity but do not necessarily keep it running. Removing the last reference ends any running instance, subject to the unresolved temporary-window lifetime rules.
- Explicit window closure and layout-driven hiding are distinct events. For Soundboard, closure stops or pauses playback even if another layout references the instance; showing it again does not automatically resume playback. Layout-driven hiding preserves playback.

### Application Lifecycle and Restoration

- First launch opens an empty workspace without a selected layout.
- Minimizing and restoring Enclave preserves running instances in memory rather than reloading them. Required background activity continues.
- Application restart restores the previously selected layout and its instances. Other layouts remain remembered and are initialized when visited, rather than starting all their instances in the background.
- Restoration reconstructs state without replaying historical commands. Modules explicitly define any activity that resumes.
- When an instance ends between layout visits, its required restoration state must survive outside that running instance.

## Rationale and Consequences

- Clear ownership prevents competing lifecycle authorities while allowing modules to implement different behavior through consistent host interactions.
- Remembered layout membership is separate from running-instance lifetime, allowing lazy initialization and later performance tuning.
- This decision refines the earlier layout requirement that modules never close or restart during switching: the guarantee is preservation of working state and required activity, not preservation of every running object.
- Modules must distinguish explicit closure, hiding, and restoration. Restoration must preserve required state without unintentionally repeating actions.
- Keeping module state separate from its UI is an option to investigate, not a selected implementation. This decision does not establish a complete third-party plugin API.

## Deferred Details

- Temporary-window lifetime and its interaction with the last-reference rule.
- Lifecycle interfaces and how modules declare capabilities.
- Inactive-instance retention and caching policies.
- Per-module state, opening defaults, saving mechanisms, and synchronization.

These details are addressed when their implementation becomes relevant; they do not change the accepted ownership and behavioral principles above.
