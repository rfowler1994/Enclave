2. **Where should responsibility sit between Enclave, a module, and its UI?**
    
    What does the host need to know to open and close a module? What does a module need from the host? Which behavior should be independent of Avalonia controls?
    
    **Why it matters:** Enclave owns shared window behavior and services; modules own specialized behavior and content. Library must discover resources even when their modules are closed. Map Viewer and Dungeon Viewer reuse image capabilities, but that does not yet establish _how_ reuse should work.
    
    **Research:** Separation of concerns, cohesion and coupling, dependency direction, interfaces, composition, MVVM, and testing behavior independently of UI.
    
    **Timing:** After clarifying ownership, define only the boundaries needed by the first module. A comprehensive module SDK, dynamic loading, and a universal messaging system can wait.

# My Understanding


# My Proposed Answer