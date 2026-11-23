A core feature of [[Enclave Overview|Enclave]] that manages the world and campaign context in which the DM is working.

Workspace Context allows modules to understand the current campaign or world while supporting resources that may be shared between multiple campaigns.

# Core Features
- Ability to create, edit, and select worlds and campaigns.
- Ability to associate multiple campaigns with the same world.
- Ability to select the active world and campaign within Enclave.
- Ability to associate resources with a specific campaign, a world, or make them available across multiple contexts.
- Enclave provides the active workspace context to modules, allowing them to determine which resources and information are relevant.
- Ability to switch between campaigns without losing their saved resources or information.
- The previously selected workspace context is restored when Enclave restarts.
# Potential Features
- Ability to configure default [[Layouts]] for specific campaigns.
- Ability to manage multiple active campaign contexts simultaneously.
- Ability to define session-specific context within a campaign, such as the current session or in-world date.
# Feature Interactions
- [[Library]]: Uses workspace context to organize and filter resources while allowing shared content to appear in multiple campaigns.
- [[Modules]]: Modules receive relevant context from Enclave and determine how it affects their functionality.
- [[Layouts]]: Potentially associates saved layouts with particular campaigns or worlds.
# Open Questions
- How should resources shared between worlds and campaigns be organized and referenced?
- What should happen to open module windows and their contents when the active campaign changes?
- Should a world exist independently of a campaign, and should campaigns be allowed to exist without an associated world?
- How should modules behave when no campaign or world is selected?