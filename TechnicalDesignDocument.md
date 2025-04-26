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
- 

## MoSCoW
- Must
  - 
- Should
  - 
- Could
  - 
- Would
  - 
