# Description

Modules are specialized components of [[Enclave Overview|Enclave]] that provide specific functionality for the DM. Each module is responsible for its own features and related data, while Enclave provides the [[Workspace Context|shared workspace]], [[Module Management|window management]], [[Layouts|layouts]], and services that allow modules to work together.

Modules can communicate and share resources through Enclave without needing to understand each other's internal implementations. Enclave's central Library provides a shared way to discover and open content managed by different modules.

A module is not necessarily a single window. Modules may open multiple windows or support multiple independent instances, depending on their functionality.
# Documentation Conventions

Each module has its own document containing:
- **Core Features:** Functionality intended for the module's initial implementation.
- **Potential Features:** Additional functionality that may be developed after the initial implementation.
- **Module Interactions:** Ways the module communicates or shares functionality with other modules. These interactions may be introduced during initial development or later.
- **Open Questions:** Unresolved decisions to investigate as development progresses.

These documents describe intended functionality rather than technical implementation. Architectural decisions and implementation details are documented separately.
# Catalog

| Module                 | Description                                                                                                                                             | Status   |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [[Party Viewer]]       | Displays active characters in a campaign's party, giving the DM quick access to character information without requiring session-by-session upkeep.      | Outlined |
| [[Dice Roller]]        | Allows the DM to roll dice and receive text-based results without graphical dice animations or simulations.                                             | Outlined |
| [[Image Viewer]]       | Allows the DM to display and interact with images using tools such as zooming, drawing, text annotations, and visual pointers                           | Outlined |
| [[Map Viewer]]         | Allows the DM to explore and manage maps of worlds, regions, cities, and other locations, with interactive markers and links to related information.    | Outlined |
| [[Dungeon Viewer]]     | Allows the DM to display and manage dungeon maps during exploration, controlling which areas and information are visible to players.                    | Outlined |
| [[Player Screen]]      | Provides a dedicated window for displaying content shared by other modules to players through a second monitor, screen sharing, or streaming software.  | Outlined |
| [[Initiative Tracker]] | Allows the DM to manage initiative order and track creatures during combat.                                                                             | Outlined |
| [[Soundboard]]         | Allows the DM to play and control music, ambience, and sound effects during a session.                                                                  | Outlined |
| [[Generators]]         | Allows the DM to quickly generate names, NPCs, loot, and other random content for session preparation or use during gameplay.                           | Outlined |
| [[Encounter Builder]]  | Allows the DM to prepare, organize, and save combat encounters for use during sessions.                                                                 | Outlined |
| [[Notes]]              | Allows the DM to create, edit, and link campaign notes using Markdown, with optional structured records for organizing more detailed world information. | Outlined |
 