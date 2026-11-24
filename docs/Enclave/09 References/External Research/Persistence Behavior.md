4. **What must survive reopening, and how will saved things retain their identity?**
    
    Separate resource content, resource references, running state, and window arrangement. What happens when the same resource appears in multiple collections or campaigns?
    
    **Why it matters:** Library requires references without duplicating content. Notes need links; maps need shared marker state; Initiative Tracker needs restoration. Workspace Context also leaves open what happens to existing windows when the campaign changes.
    
    **Research:** Stable identifiers, references versus copies, serialization, files versus embedded databases, atomic saves, schema evolution, and context scoping.
    
    **Timing:** Decide the first module’s persistence behavior before implementing saving. Research identity before implementing cross-resource links. The complete Library schema, indexing, and advanced migration machinery can wait.