3. **What does “window” mean in Enclave, and what must the UI framework demonstrate?**
    
    How do freely arranged workspace windows relate to operating-system windows? Can a view be hidden without ending its underlying activity?
    
    **Why it matters:** Snapping, clamping, overlapping, temporary windows, and layout restoration shape the workspace UI. Player Screen also requires a stable external capture target. General window detachment is listed as potential functionality, so it need not become an initial requirement.
    
    **Research:** Avalonia controls versus top-level windows, UI composition, focus and input routing, layout coordinates, view lifetimes, and small feasibility prototypes.
    
    **Timing:** Explore alongside question 2, before investing heavily in the workspace shell. Full snapping behavior and cross-platform capture validation can wait until their implementation approaches.