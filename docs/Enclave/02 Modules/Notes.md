A [[Modules|module]] that allows the DM to create, edit, and link campaign notes using Markdown, with optional structured records for organizing more detailed world information.

Notes follows the principle of "improvisation first, structure second," allowing users to capture information freely and introduce structure only when it becomes useful.
# Quick Notes (Initial Implementation)
## Core Features
- Ability to create, edit, save, and delete Markdown notes.
- Ability to write and view formatted Markdown content, including embedded images.
- Ability to create links between notes and navigate directly between them.
- Ability to open multiple notes in separate windows through [[Module Management]].
- Notes remain accessible through Enclave's central Library rather than requiring a separate note explorer.
## Potential Features
- Ability to view backlinks showing which other notes reference the current note.
- Ability to view and navigate a note's revision history.
- Ability to embed content from other notes.
- Ability to create reusable Markdown templates for quickly starting new notes.
# Typed Entities (Future Implementation)
## Core Features
- Ability to create and manage customizable Types, such as NPCs, locations, factions, and items.
- Ability to define fields and their properties within a Type, supporting different types of information, including images.
- Ability to create, edit, and delete Entities based on a selected Type.
- Entities created from the same Type share a common structure while maintaining their own information.
- Every Entity includes a freeform Markdown section for additional information that does not fit its structured fields.
- Ability to reference other notes and Entities through supported fields.
- Ability to modify Types without losing existing Entity information:
    - New fields support a configurable default value, including blank, for existing and future Entities. 
    - Removing a field preserves existing nonempty values, even when the field is no longer defined by the Type.    
    - Preserved fields are distinguishable from fields currently defined by the Type.
## Potential Features
- Ability to create one or more Entities using information extracted from an existing Quick Note without modifying the original note.
- Ability to identify and list existing Entities affected by changes to a Type.
- Ability to customize how Entities are displayed through a visual layout editor, arranging fields, images, and Markdown content into wiki-style pages.
- Advanced field types, validation rules, and customizable field behavior.
- Ability to search and filter Entities using their structured fields.
- Ability to create relationships between Entities and explore those relationships.
- Advanced handling of Type changes, including converting existing field values when field definitions change.
- Ability to import and export Types for sharing between users.
# Module Interactions
- [[Enclave Overview|Enclave]]: Provides central Library navigation, organization, and search for both Quick Notes and Typed Entities.
- [[Party Viewer]]: Opens notes associated with party characters.
- [[Map Viewer]]: Allows map markers to reference and open related notes.
- [[Dungeon Viewer]]: Potentially associates dungeon locations or rooms with related notes.
- [[Encounter Builder]]: Opens notes associated with encounters and creatures.
- [[Generators]]: Potentially uses Markdown templates or Type definitions to structure generated content and create notes or Entities.
- [[Player Screen]]: Allows the DM to share an image embedded in a note directly with players, without sharing the entire note.
- Other modules may reference and open Quick Notes or Typed Entities without managing their content directly.
# Open Questions
- How should Quick Notes and Typed Entities share common capabilities, such as Markdown editing and linking?
- How should changes to field types affect existing Entity values?
- How should Markdown text, structured fields, and images be presented together in the initial Typed Entity interface?
- How should links between notes, Entities, and resources from other modules behave?