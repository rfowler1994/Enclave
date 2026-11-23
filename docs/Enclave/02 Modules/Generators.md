A [[Modules|module]] that allows the DM to quickly generate names, NPCs, loot, and other random content for session preparation or use during gameplay.
# Core Features
- Ability to select and run different types of generators, including names, NPCs, loot, and random tables.
- Ability to generate new results without closing or reopening a generator.
- Ability to copy generated results for use elsewhere.
- Generators function offline without requiring external services or AI.
# Potential Features
- Ability to create, edit, and save custom generators and random tables, including weighted probabilities.
- Ability to import and export custom generators for sharing.
- Ability to define optional world and regional characteristics, such as population demographics, magic prevalence, and other setting-specific information.
- Ability to configure generators to consider defined world information and additional parameters when determining results. For example:
    - NPC generation influenced by a region's population demographics.
    - Loot generation influenced by a setting's magic prevalence.
- Ability to associate generators with templates from [[Notes]], allowing generated content to follow a selected template's structure.
- Ability to save generated results for future reference.
- Ability to combine multiple generators to produce more complex results.
- Optional LLM integration, allowing the DM to connect a supported AI provider to assist with generation while retaining offline functionality.
# Module Interactions
- [[Notes]]: Potentially uses note templates to structure generated content and allows generated results to be saved as notes.
- [[Encounter Builder]]: Potentially provides generated creatures, loot, or encounter ideas.
# Open Questions
- Which generators and result fields should be included initially?
- How should custom generators and their probabilities be defined?
- How should world and regional information be organized, inherited, and used by generators?
- How should generators interact with custom note templates, particularly when templates contain fields that a generator does not recognize?
- How should external LLM providers be configured, and what information should be provided to them during generation?