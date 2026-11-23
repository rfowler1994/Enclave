A [[Modules|module]] that allows the DM to display and interact with images using tools such as zooming, drawing, text annotations, and visual pointers.
# Core Features
- Ability to open and view an image
- Ability to open multiple Image Viewer instances through [[Module Management]].
- Ability to pan and zoom around an image.
- Ability to fit an image to the window, adjusting the zoom so the entire image is visible.
- Ability to draw and add text annotations over an image.
- Ability to clear all drawings and text annotations.
- Ability to undo the most recent drawing or text annotation.
- Ability to ping a location on an image, displaying a temporary ripple effect to draw attention to that location.
- Ability to use a movable laser pointer to draw attention to areas of an image.
# Potential Features
- Ability to save an image with its drawings and text annotations.
- Ability to mark drawings and text annotations as DM-only or public, preventing DM-only content from appearing in [[Player Screen]].
- When sharing an image, [[Player Screen]] follows the DM's pan and zoom by default, with an option to navigate independently.

# Module Interactions
- [[Dungeon Viewer]] and [[Map Viewer]]: Reuse Image Viewer's core viewing and interaction capabilities while providing their own specialized features. 
- [[Player Screen]]: Shares a live, player-visible version of the image, including public annotations, pings, and laser pointer movements.
# Open Questions
- Which image formats should be supported beyond JPG and PNG?
- What drawing options should be available? Initial ideas include color, thickness, and opacity.
- What text annotation options should be available? Initial ideas include color, font, font size, and opacity. How should available fonts be managed?
- What should happen when the same image is opened in multiple Image Viewer instances? Should annotations be shared or independent?
