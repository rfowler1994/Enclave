5. **Which first module and end-to-end workflow will test enough of the foundation?**
    
    What should a user be able to do from opening Enclave through using the module, closing it, and reopening it?
    
    **Why it matters:** The first module determines which architectural questions need concrete answers now. Dice Roller has no planned core module interactions, so it can exercise hosting and UI separation but provides limited evidence about resource discovery. Quick Notes exercises saving, linking, multiple windows, and Library access, bringing considerably more dependencies.
    
    **Research:** Vertical slices, evolutionary architecture, acceptance scenarios, and risk-focused prototypes.
    
    **Timing:** Choose this before committing to a foundation implementation. You do not need to select the order of every subsequent module.