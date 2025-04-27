# Technical Design Document (TDD)
This plugin is made for Minecraft Java 1.20.2 servers using Paper as the server API and Maven as the build system.

## General Implementation Plan
- Commands and tab completion:
  - Using the traditional Bukkit command system:
    - Define commands in `plugin.yml`.
    - Register a command executors manually in `OnEnable()`.
    - Register a tab completers manually in `OnEnable()`.
    - Handle command execution logic in classes that implement `CommandExecutor`.
    - Handle tab completion logic in classes that implement `TabCompleter`.
  - Automation using Java Annotations:
    - Use custom annotations (`@CommandHandler` and `CommandCompleter`) to define command handling and tab completion methods.
    - During plugin initialization, use reflection to scan command classes for methods annotated with `@CommandHandler` or `CommandCompleter`.
    - Automatically register commands and tab completers based on these annotations.
    - Centralize all command and tab completion logic inside one class for easier maintenance and scalabillity.
    - When a command is executed:
      - Search at runtime for a method annotated with `@CommandHandler` matching the command name.
      - Validate the sender type and permissions based on the annotation.
      - Dynamically invoke the matching method using reflection to process the command.
    - When tab completion is requested:
      - Search at runtime for a method annotated with `@CommandCompleter` matching the command name.
      - Validate permissions based on the annotation.
      - Dynamically invoke the matching method using reflection to process the tab completion.
- Claims:
  - Establish a stable database connection to allow saving and loading player and claim data.
  - Creating a claim (`/claim` or `/claim create`):
    - Save the player's current inventory
    - Give the player a claim creation inventory with the necessary tools to make a selection and cancel or confirm the creation.
    - Display a boundary around the selected area.
    - On confirmation, save the claim to the database and restore the player's original inventory.
    - On cancel, restore the player's original inventory.
  - Deleting claims (`/claim delete`):
    - Validate whether the player is within a claim.
    - Validate whether the player is the owner of the claim or has permissions.
    - Delete the claim form the database.

## MoSCoW
- Must
  - Establish a stable database connection
  - Make a `/claim` command with optional parameters `delete` and `info`.
- Should
  - Add `trust` as a parameter to the `/claim` command.
- Could
  - 
- Would
  - 
