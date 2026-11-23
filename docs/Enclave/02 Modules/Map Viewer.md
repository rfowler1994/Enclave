A [[Modules|module]] that allows the DM to explore and manage maps of worlds, regions, cities, and other locations, with interactive markers and links to related information.
# Core Features
- Ability to open and view a map using the viewing and interaction capabilities of [[Image Viewer]].
- Ability to open multiple Map Viewer instances through [[Module Management]].
- Ability to add, edit, move, and remove markers at specific locations on a map.
- Ability to assign names and descriptions to markers.
- Ability to open information associated with a marker.
- Ability to save maps and their markers for future use.
- Changes to map markers are reflected across all instances displaying the same map.
# Potential Features
- Ability to organize markers into categories, such as settlements, landmarks, and points of interest.
- Ability to control which markers are visible to players when sharing a map through [[Player Screen]].
- Ability to navigate between related maps, such as opening a city map from a marker on a regional map.
- Ability to configure a minimum zoom level for each marker, automatically hiding it when zoomed out beyond that threshold.
- Ability to have different icons or visual styles for map markers.
# Module Interactions
- [[Image Viewer]]: Reuses core image viewing and interaction capabilities, including pan, zoom, annotations, pings, and laser pointers.
- [[Notes]]: Allows markers to reference and open related notes, such as locations, settlements, and landmarks.
- [[Player Screen]]: Shares a live, player-visible map and its interactions.

# Open Questions
- What information should a marker store beyond its name, description, and associated notes?
- Should multiple instances displaying the same map maintain independent pan and zoom positions?