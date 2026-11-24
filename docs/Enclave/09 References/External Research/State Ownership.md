# Question Asked
Source: ChatGPT Architectural review

1. **What owns each kind of state, and how long should it live?**
    
    Distinguish a module definition, a running module instance, its windows, and its saved resources.
    
    **Why it matters:** Hiding a window must preserve activity; closing Soundboard stops playback; closing Initiative Tracker must preserve combat for reopening. Map Viewer instances share marker changes, while some viewing state may be independent. Treating these as one lifetime would make those requirements difficult to reconcile.
    
    **Research:** State ownership, object identity, lifecycle state machines, transient versus persistent state, cancellation and disposal.
    
    **Timing:** Investigate first. Establish behavior for the first module before designing its objects or connecting its lifetime to UI controls. Other modules can retain unanswered details.



# My Understanding
State - The information describing something at a particular moment. For example, a combat's current round, a window's position, or whether a sound is playing.
State Ownership - Who is responsible for maintaining the state information. 
Lifecycle - When something is created, becomes active, becomes inactive, and ends.
Persistent State - Information saved so it can survive the end of the running object or application and be restored later. In Enclave, also distinguish what survives closing a module from what survives exiting Enclave.

# My Proposed Answer
I imagine we solve state ownership by splitting up the responsibility between Enclave and Modules. For example Enclave would be responsible for maintaining which modules are open and their positions/sizing. While Modules will be responsible for the content that is displayed within them. 

How I imagine the different lifecycles of Enclave as a whole working:
- Open - The application opens to an empty workspace and no layout.
- Hide - The application retains every module position and size that is open. The modules are responsible for the content.
- Show - All modules are loaded back to where they were before the application was minimized. Load might be the wrong word here. I imagine hide/show in the context of Enclave being like hitting the minimize button in Windows appliations. I wouldn't want everything to have to reload because they minimized for a second. 
- Close - The application retains every module position and size that is open. The modules are responsible for the content.
- Application Restart - All modules are loaded back to where they were before the application was closed.

How I imagine the different lifecycles of individual modules working: 
As a note I think this depends a lot on the specific modules. I will try to explain the main options I could see the different modules working.
- Module opened - The module launches to it's *default* view. For example:
	- Dice - Just display it's dice UI
	- Image Viewer - If module was opened by the user selecting an image it would open that image. If the module was opened with no selection made then the user would see a way to search images in the user's Enclave and potentially a way to see recently opened. 
- Module hidden - I'm not entirely sure if I want to support the ability to hide a module. I imagine this working like you hit minimize on a normal windows application. My problem is I can't picture where that goes in context of Enclave. I'm leaning towards there are compact, and expanded views of modules and then they can be closed. I guess there could be a world where hidden show up as tabs, bars, or buttons somewhere on screen but unsure I want to have that functionality. So for this state, currently we will mimic the module close state. 
- Module show - Similar to my explanation under module hidden we would mimic the module reopen state. 
- Module close - The module would save the information currently being displayed before closing. For example: 
	- Dice - Saves the dice history 
	- Dungeon Viewer - Saves the current dungeon image, all token positions, all notes, all visibility settings. 
- Module reopened - The module loads the information that was displayed for closing as defined in module close.
- Application restart - If the module was open when the application was closed. It should be reopened as explained in lifecycles of Enclave above. And then it should function the same as module reopened explained just above this.

# Modules Design

Use this checklist when designing each module's state and lifecycle. Answers describe how the module participates in Enclave's shared contract; they do not redefine Enclave's ownership or layout rules. Not every question applies to every module.

| Area | Questions to ask |
| --- | --- |
| **Instances and identity** | Is the module single-instance or multi-instance? What distinguishes one instance from another and preserves its identity during restoration? What does “open another” mean? |
| **Opening and resource selection** | What appears in a fresh instance? What happens when opening a specific resource? When should an existing instance be reused rather than creating or restoring one? |
| **Windows and views** | Can one instance have multiple windows? What state belongs to each view? Does the module use temporary windows, and what should happen when they close under Enclave's eventual temporary-window rules? |
| **State ownership** | What information belongs to the saved resource, running instance, individual view, or workspace? Who is authoritative for each fact, who may request changes, and what rules govern those changes? |
| **Shared content** | Can separate instances display the same saved resource? Which changes must appear across instances, and which state remains independent? How are saving content and updating other running instances distinguished? |
| **Host contract and services** | Which capabilities must the module declare, including instance limits and background requirements? Which Enclave services does it need? Can it use the shared lifecycle and service contract without module-specific branches in Enclave? |
| **Visibility and background activity** | What continues when windows are hidden by layout switching or Enclave is minimized? What work can pause? Determine this independently of instance limits. What happens when an existing instance becomes visible again? |
| **Explicit closure and termination** | How does the module respond differently to explicit window closure, layout-driven hiding, and instance termination? What stops or pauses when a window is removed but the instance remains? What must be preserved when Enclave ends the instance? |
| **Restoration** | What must return after closure, after ending an inactive instance between layout visits, and after application restart? What must appear unchanged? What information must survive outside the running instance, and what does Enclave need to request restoration? Which activities, if any, explicitly resume, without replaying historical commands? |
| **Layouts and campaigns** | Under Enclave's shared layout rules, what differs between separate instances and what follows the same resource? Is content tied to a world or campaign? What happens to open content and activity when the active campaign changes? |
| **Saving and failure** | When are changes saved? What should survive an unexpected exit? What happens if saving, initialization, or restoration fails, or a referenced resource is missing? |
| **Cleanup** | What files, audio, timers, event subscriptions, background work, or graphics resources must be released when a view is removed or an instance ends? Which resources must remain for continued activity or restoration? |

# Refined Proposal

The principles below were accepted as Enclave's current plan in [[ADR-001 State Ownership and Module Lifecycle Responsibilities]]. That ADR is the authoritative decision record; this section preserves the research summary. Implementation mechanisms remain undecided.

## Ownership and Identity

- **Enclave** owns workspace state: instance tracking, window position, size and visibility, layout membership, and coordination of instance creation, closure, and restoration.
- **Single source of truth:** Enclave is authoritative for window and instance lifecycle state. Modules may request lifecycle changes; Enclave determines the transition and modules respond with their specialized behavior.
- **Modules** own their specialized state and behavior, including what must be preserved and how they respond to lifecycle events. Enclave remembers enough information to request restoration without interpreting module content.
- A **module definition**, **module instance**, **window**, and **saved resource** are distinct concepts with potentially different lifetimes.
- **Single-instance** modules can share one instance across layouts. **Multi-instance** modules use separate instances in different layouts; those instances may still display the same saved resource.
- **Instance limits** and **background activity** are separate module characteristics.

## Application Lifecycle

- First launch opens an empty workspace without a selected layout.
- **Minimize/restore** preserves running instances in memory; restoring visibility does not reload them. Required activity, such as audio playback and Player Screen updates, continues.
- On application restart, Enclave restores the previously selected layout and its instances. Other layouts remain remembered and are initialized when needed (**lazy initialization**); their instances are not all started in the background.
- **State restoration** does not replay historical **commands** or inherently resume previous activity. Modules explicitly define any activity that resumes during restoration.

## Layouts and Instance Lifecycle

- Layout switching preserves the user's working state. Modules declare whether they require continued activity while hidden. Other instances may be retained or ended and restored, provided their required state survives. The **retention policy** remains undecided.
- **Creating a fresh instance** and **restoring a remembered instance** are different operations. Module-specific opening defaults can be defined later.
- Explicitly closing a window removes it from the current layout. References in other layouts preserve its remembered identity, but do not necessarily require it to remain running. Removing the last reference ends any running instance, subject to the unresolved temporary-window case below.
- **Explicit closure** and **hiding during layout switching** are different events. For Soundboard, explicit closure stops or pauses playback even if another layout references the instance; showing it again does not automatically resume playback. Hiding through layout switching preserves playback.
- If an instance ends between layout visits, its required restoration state must survive outside that running instance.

## Open or Deferred Questions

- **Temporary windows:** What keeps their instances alive without saved layout membership, and when does closing them end the instance?
- **Lifecycle contract:** How do modules declare background requirements and participate in closure and restoration?
- **Retention policy:** Whether to retain inactive instances, including caching recently used layouts, remains deferred until implementation and measurements justify a policy.
- Per-module state details and opening defaults remain deferred to module design. Saving mechanisms and synchronization are outside this proposal.
