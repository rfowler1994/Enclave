A minimal [[Modules|module]] that allows the DM to manage initiative order and track creatures during combat.
# Core Features
- Ability to open multiple Initiative Tracker instances through [[Module Management]], each managing an independent combat.
- Ability to start and end combat, clearing the current combat when ended.
- Ability to add or remove creatures before or during combat, identifying them as allies or enemies.
- Ability to manually enter initiative values and automatically sort creatures into initiative order.
- Ability to track the current creature's turn and advance to the next turn, automatically progressing the round when the initiative order cycles.
- Ability to manually add and remove conditions on creatures, such as stunned, prone, or concentrating.
- Each instance maintains its own combat state, which persists when the module is closed or [[Enclave Overview|Enclave]] restarts.
# Potential Features
- Ability to manually reorder creatures using drag and drop.
- Ability to track creature hit points.
- Ability to add creatures directly from [[Dungeon Viewer]].
- Ability to synchronize creature conditions with [[Dungeon Viewer]], reflecting changes made in either module.
- Ability to designate creatures as concealed or hidden when shared through [[Player Screen]]. Concealed creatures appear as question-mark placeholders, while hidden creatures are not displayed.
# Module Interactions
- [[Party Viewer]]: Automatically imports party characters when combat starts and allows the DM to open their character sheets.
- [[Player Screen]]: Shares a player-visible version of the initiative tracker.
- [[Encounter Builder]]: Starts combat using a prepared encounter and displays scheduled encounter reminders when their associated rounds are reached.
# Open Questions

