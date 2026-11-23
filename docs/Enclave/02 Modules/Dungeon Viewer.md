A [[Modules|module]] that allows the DM to display and manage dungeon maps during exploration, controlling which areas and information are visible to players.
# Core Features
- Ability to open and view a dungeon map using the viewing and interaction capabilities of [[Image Viewer]].
- Ability to open multiple Dungeon Viewer instances through [[Module Management]].
- Ability to hide and reveal portions of a dungeon map using fog of war.
- Ability to manually reveal or conceal areas by drawing or selecting larger shapes.
- Ability to save the dungeon's exploration state so previously revealed areas remain visible when reopened.
- Ability to reset the dungeon's exploration state.
- Ability to configure a square or hexagonal grid, including its size, when opening a dungeon for the first time.
- Grid configuration is saved and restored when the dungeon is reopened.
# Potential Features
- Ability to define rooms or regions that can be revealed individually.
- Ability to place and move tokens representing player characters, creatures, or other objects.
- Ability to assign visibility settings to individual tokens or other map elements.
- Ability to manage multiple floors or connected dungeon maps.
- Ability to automate parts of exploration, such as revealing areas based on token movement.
- Ability to add conditions to creatures or players tokens.
# Module Interactions
- [[Image Viewer]]: Reuses core image viewing and interaction capabilities, including pan, zoom, annotations, pings, and laser pointers.
- [[Player Screen]]: Shares a live, player-visible dungeon map, reflecting changes to fog of war and other public interactions.
- [[Party Viewer]]: Potentially allows character portraits to be dragged onto the dungeon as player tokens.
- [[Notes]]: Potentially allows dungeon locations or rooms to reference related notes.

# Open Questions
- Should previously revealed areas be distinguishable from areas currently visible to players?
- How should the DM view hidden areas while keeping them concealed from players?
- How should multiple instances of the same dungeon handle exploration state and other changes?