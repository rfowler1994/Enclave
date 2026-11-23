A core feature of [[Enclave Overview|Enclave]] that provides a flexible window management system for displaying and interacting with [[Modules]].

Windows can be freely arranged, resized, and anchored within the Enclave workspace, allowing DMs to organize their tools without being restricted to a fixed interface.

# Core Features
- Ability to open, close, move, and resize module windows.
- Ability to display multiple windows simultaneously, including windows from the same module when supported.
- Ability to freely position windows within the Enclave workspace.
- Ability to snap windows to other windows or workspace boundaries for easier alignment.
- Ability to clamp or anchor windows to the edges of the Enclave workspace, such as positioning [[Party Viewer]] along one side.
- Ability to reduce window borders and other visual elements when windows are inactive, minimizing distractions and maximizing usable space.
- Support for temporary windows that can be opened for quick interactions without permanently changing the current [[Layouts|layout]].
- Ability to pin a temporary window, making it part of the current saved layout.
- Windows retain their contents and relevant state when temporarily hidden, including when switching layouts.
- Enclave provides consistent window controls and behavior while modules manage the content displayed within their windows.
# Potential Features
- Ability to configure window transparency or opacity.
- Ability to lock individual windows to prevent accidental movement or resizing.
- Ability to configure whether specific windows remain above others.
- Ability to customize window borders, decorations, and other visual preferences.
- Support for detaching windows from the main Enclave workspace for use on additional monitors.
# Feature Interactions
- [[Layouts]]: Saves window positions, sizes, and visibility as part of configurable workspace arrangements.
- [[Module Management]]: Coordinates window creation and closure with module instances and their lifecycles.
- [[Modules]]: Modules provide window content while Enclave handles shared window behavior.
- [[Player Screen]]: Requires a persistent, reliably identifiable window for external screen capture.
# Open Questions
- Should windows be restricted to the main Enclave workspace, or should some be allowed to move outside it?
- How should snapping and clamping behave when the main Enclave window is resized?
- What determines whether a window is temporary or part of a saved layout?
- How should closing a window differ from closing its associated module instance?
- How should window focus and overlapping windows be managed?