A [[Modules|module]] that displays active characters in a campaign's party, giving the DM quick access to character information without requiring session-by-session upkeep.
# Core Features
- Configuration options for the DM to add a character to the party and define the following attributes:
    - Character's name
    - Portrait
    - Link to D&D Beyond
    - Name of the character's note in the [[Notes]] module
- The Party Viewer can be clamped to a side of the [[Enclave Overview|Enclave]] window using Enclave's [[Windows|window management]] functionality.
- The Party Viewer provides a compact view of the characters' portraits.
- Interacting with a character's portrait allows the DM to open a new window in [[Enclave Overview|Enclave]] displaying the character's D&D Beyond sheet in an embedded browser. An embedded browser is the preferred approach for accessing the character's current sheet.
- Interacting with a character's portrait allows the DM to open the character's linked note through the [[Notes]] module.
# Potential Features
- The ability to drag a character's portrait onto the [[Dungeon Viewer]] to add a token for that character to the active dungeon. This would introduce a new module interaction with the [[Dungeon Viewer]].
# Module Interactions
- Open a [[Notes]] window displaying the requested character's note.
# Open Questions
- Can D&D Beyond character sheets be reliably displayed in an embedded browser? If not, opening them in an external browser is an acceptable alternative.
- How can an embedded browser securely retain D&D Beyond login sessions? Occasional logins are acceptable, but ideally no more than once per game session.