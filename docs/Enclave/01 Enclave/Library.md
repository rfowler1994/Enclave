# Description

A core feature of [[Enclave Overview|Enclave]] that provides a centralized way to discover, organize, search, and open resources managed by different [[Modules]].

Library acts as a shared resource explorer without replacing the specialized functionality of individual modules. Modules remain responsible for their content, while Library provides a consistent way to access it.
# Core Features
- Ability to browse and search saved resources across supported modules, including notes, maps, dungeons, and encounters.
- Ability to identify resources by their name and type.
- Ability to open a resource in its corresponding module.
- Ability to organize resources into folders or collections.
- Ability to associate the same resource with multiple folders or collections without duplicating its underlying content.
- Ability to create, rename, and remove folders or collections without affecting resources referenced elsewhere.
- Ability to filter resources based on the active world or campaign through [[Workspace Context]].
- Resources remain accessible through Library regardless of whether their associated modules are currently open.
# Potential Features
- Ability to search within resource contents, where supported by the owning module.
- Ability to assign tags or other organizational metadata to resources.
- Ability to preview resources without fully opening their associated modules.
- Ability to open multiple resources from a folder or collection simultaneously.
- Ability to configure folders or collections to open specific resources together, such as a city note and its associated map.
- Ability to save frequently used searches or resource collections for quick access.
- Ability to display recently opened or frequently accessed resources.
# Feature Interactions
- [[Modules]]: Modules make their saved resources discoverable through Library while retaining responsibility for their content.
- [[Module Management]]: Opens the appropriate module when a resource is selected.
- [[Windows]]: Displays opened resources in their corresponding module windows.
- [[Workspace Context]]: Determines which resources are relevant to the active world or campaign.
- [[Layouts]]: Potentially allows collections of resources to be opened within a particular layout.
# Open Questions
- How should resources be identified and referenced consistently across different modules?
- Should Library use traditional folders, flexible collections, or support both?
- How should resources shared between multiple worlds, campaigns, and collections be displayed?
- How should searching work across modules that manage different types of information?
- How should deleting a resource differ from removing it from a folder or collection?
- How should Library handle resources belonging to modules that are unavailable or disabled?