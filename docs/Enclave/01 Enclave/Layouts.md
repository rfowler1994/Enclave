# Description

A core feature of [[Enclave Overview|Enclave]] that allows the DM to create and switch between customized workspace arrangements for different activities, such as combat, roleplay, and session preparation.

Layouts define which module windows are visible and how they are arranged without interrupting the underlying modules or their active state.
# Core Features
- Ability to create, rename, delete, and save multiple named layouts without a fixed limit.
- Ability to switch between saved layouts without closing or restarting active modules.
- Each layout remembers the windows it contains, including their positions, sizes, and visibility.
- Switching layouts hides windows not included in the selected layout while preserving their contents and state.
- Ability to enter a layout editing mode to add, remove, reposition, and resize windows within a saved layout.
- Ability to open temporary windows without modifying the current layout.
- Ability to pin temporary windows to the current layout, making them part of its saved arrangement.
- Ability to restore saved layouts when [[Enclave Overview|Enclave]] restarts.
# Potential Features
- Ability to duplicate an existing layout as a starting point for a new one.
- Ability to import and export layouts for sharing or backup.
- Ability to assign keyboard shortcuts for switching between layouts.
- Ability to associate layouts with specific campaigns or worlds through [[Workspace Context]].
- Ability to create reusable layout templates.
# Feature Interactions
- [[Windows]]: Uses Enclave's window management functionality to position, resize, show, and hide windows.
- [[Module Management]]: Preserves module instances and their state when switching between layouts.
- [[Workspace Context]]: Potentially provides campaign- or world-specific layouts.
# Open Questions
- Can the same module window belong to multiple layouts, or should each layout maintain its own windows?
- What happens to temporary windows when switching layouts?
- How should changes to a window outside editing mode affect its saved layout?
- How should layouts behave when the Enclave window or available screen space changes size?
- Should each layout remember which window was last focused?