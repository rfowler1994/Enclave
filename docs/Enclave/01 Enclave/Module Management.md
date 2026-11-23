# Description

A core feature of [[Enclave Overview|Enclave]] responsible for discovering, opening, closing, and managing [[Modules]] and their instances.

Module Management allows modules to operate independently while providing access to Enclave's shared workspace functionality.
# Core Features
- Ability to browse available built-in modules and open them within Enclave.
- Ability to open and close module instances without restarting Enclave.
- Individual modules determine whether they support a single instance or multiple independent instances.
- Ability to manage multiple active modules simultaneously.
- Closing a module instance ends its active operations and closes its associated windows.
- Modules remain active when their windows are hidden or inactive, including when switching [[Layouts]].
- Modules can create and manage windows through Enclave's shared [[Windows|window management]] functionality.
- Enclave provides modules with access to shared functionality, such as [[Workspace Context]], [[Library]], and other common services.
# Potential Features
- Support for installing and loading third-party modules.
- Ability to enable, disable, and uninstall optional modules.
- Ability to browse and install community-created modules through an integrated module marketplace.
- Ability to configure module-specific settings through a consistent Enclave interface.
- Ability to import and export module configurations.
- Support for managing module updates and compatibility with different Enclave versions.
# Feature Interactions
- [[Modules]]: Defines the modules available within Enclave and their individual functionality.
- [[Windows]]: Manages the windows associated with active module instances.
- [[Layouts]]: Determines which module windows are visible without interrupting active modules.
- [[Workspace Context]]: Provides modules with relevant world and campaign information.
- [[Library]]: Allows saved resources to be opened through their corresponding modules.
# Open Questions
- How should module instances and their associated windows be managed throughout their lifecycle?
- Which module settings and states should persist between Enclave sessions?
- How should modules communicate with Enclave and other modules without depending on their internal implementations?
- Can built-in and third-party modules use the same interfaces and shared functionality?
- How should third-party module permissions, security, and compatibility be handled?
- What restrictions should exist on installing, disabling, or removing modules that other modules depend on?