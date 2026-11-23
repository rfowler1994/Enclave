A [[Modules|module]] that allows the DM to prepare, organize, and save combat encounters for use during sessions.
# Core Features
- Ability to create, edit, delete, and reuse saved combat encounters.
- Ability to add and remove creatures, specifying their names, quantities, and whether they are allies or enemies.
- Ability to associate creatures with D&D Beyond stat blocks and related notes from [[Notes]].
- Ability to add encounter notes, including combat tactics, environmental hazards, and other relevant information.
- Ability to define events or reminders associated with specific combat rounds, such as reinforcements arriving or environmental changes.
- Ability to define treasure and other rewards associated with an encounter.
# Potential Features
- Ability to calculate encounter difficulty using D&D 5.5e encounter-building rules.
- Support for additional tabletop systems or customizable encounter difficulty calculations.
- Ability to calculate experience point rewards.
- Ability to organize encounters into categories or groups.
- Ability to create and reuse encounter templates.
- Ability to generate random encounters based on configurable criteria.
- Ability to drag creatures from an encounter directly onto [[Dungeon Viewer]] as tokens.
# Module Interactions
- [[Initiative Tracker]]: Starts combat using an independent copy of the prepared encounter, including its creatures and relevant encounter information. Displays scheduled reminders when their associated rounds are reached.
- [[Notes]]: Opens notes associated with creatures or other encounter information.
- [[Party Viewer]]: Potentially uses party composition and character information when calculating encounter difficulty.
- [[Generators]]: Potentially generates encounters, creatures, treasure, and other rewards.
- [[Dungeon Viewer]]: Potentially allows creatures from an encounter to be added as dungeon tokens.
# Open Questions
- What additional creature information should be stored within an encounter?
- How should encounter events and reminders be managed during active combat?
- How should encounter difficulty calculations handle missing or customized creature statistics?