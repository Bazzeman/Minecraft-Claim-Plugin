# Technical Design Document (TDD)
This plugin is made for Minecraft Java 1.20.2 servers using Paper as the server API and Maven as the build system.

## General Implementation Plan
- Commands such as `/claim`, `/unclaim` and `/trust`:
  - Using the legacy Bukkit command system; includes registering and unregistering commands and tab completers and their handlers.
  - Automation using Java Annotations; simply add a annotation to a method to use it as a typical command handler or tab completer, registering and unregistering will be automated.

Going to finish this file this evening!
