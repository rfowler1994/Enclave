A [[Modules|module]] that provides a dedicated window for displaying content shared by other modules to players through a second monitor, screen sharing, or streaming software.
# Core Features
- Ability to display player-visible content shared by supported modules.
- Only one instance of Player Screen can be open at a time.
- Player Screen maintains a consistent window identity, allowing external applications such as OBS or Discord to capture it without requiring reconfiguration when shared content changes.
- Ability to switch between shared content from different modules, replacing the currently displayed content without reopening the Player Screen window.
- Ability to display live updates from the source module, including interactions and changes intended to be visible to players.
- Only content explicitly shared by the DM is displayed.
- Content designated as DM-only by the source module must not appear in Player Screen.
- Player Screen displays shared content without the source module's DM-specific editing controls.
# Potential Features
- Ability to display content from multiple modules simultaneously, rather than replacing the currently displayed content. How multiple sources would be arranged and managed has not yet been determined.
- Ability to quickly switch between previously shared sources without requiring the DM to share them again from their original modules.
# Module Interactions
- [[Image Viewer]]: Displays shared images and player-visible interactions, including annotations, pings, and laser pointer movements.
- [[Map Viewer]]: Displays shared maps and player-visible map elements.
- [[Dungeon Viewer]]: Displays shared dungeons and player-visible exploration changes.
# Open Questions
- How should Player Screen handle differences between the DM's view and the player-visible view, such as synchronized or independent pan and zoom?
- How can Player Screen maintain a reliable capture target across supported operating systems and capture applications?