# Project Brief: Copilot Memory Bank

## 1. Project Goal

To adapt the principles of the Cline Memory Bank system to leverage GitHub Copilot's built-in customization features (`.github/copilot-instructions.md` and potentially `*.prompt.md` files). The aim is to provide GitHub Copilot with persistent, structured, and evolving project context within a specific repository, enhancing its understanding and the relevance of its responses.

## 2. Problem Statement

While GitHub Copilot is powerful, maintaining deep and structured project context (like architectural decisions, product goals, tech stack specifics, current progress) across multiple chat interactions can be challenging. Users often need to repeat context. Existing customization features like Repository Instructions (`.github/copilot-instructions.md`) offer a way to inject context, but adapting the comprehensive, multi-file structure of the Cline Memory Bank to this mechanism requires a dedicated approach.

## 3. Proposed Solution: "Copilot Memory Bank"

This project will define and implement a system that uses GitHub Copilot's customization features to mimic the benefits of the Cline Memory Bank:

1.  **Context Structure:** Define a standardized structure for essential project context (inspired by Cline's `productContext`, `techContext`, `systemPatterns`, `activeContext`, `progress` files).
2.  **Implementation Strategy:**
    *   Investigate the most effective way to represent this structured context within or referenced by the single `.github/copilot-instructions.md` file, respecting potential limitations. This might involve:
        *   Condensing key information directly into `copilot-instructions.md`.
        *   Instructing Copilot within `copilot-instructions.md` to prioritize information from a dedicated `memory-bank/` directory containing structured Markdown files (testing the limits of this approach).
    *   Explore using `*.prompt.md` files (e.g., in `.github/prompts/`) for specific tasks that require deeper context from the "Memory Bank" files (e.g., "Draft API documentation based on `memory-bank/systemPatterns.md`").
3.  **Workflows:** Define practical workflows for initializing, maintaining, and updating the context within the Copilot ecosystem.
4.  **Documentation:** Create clear guidelines on how to set up and use the Copilot Memory Bank system.

## 4. Scope

*   **In Scope:**
    *   Defining a context structure suitable for Copilot.
    *   Implementing the core context injection using `.github/copilot-instructions.md`.
    *   Developing example `*.prompt.md` files for context-aware tasks.
    *   Creating setup and usage documentation.
    *   Focusing on repository-level context within VS Code.
    *   Providing a functional example within this repository.
*   **Out of Scope:**
    *   Creating a separate VS Code extension.
    *   Perfectly replicating all Cline behaviors (due to platform differences).
    *   Supporting context outside of a Git repository.

## 5. Success Criteria

*   A clearly defined and documented structure for the Copilot Memory Bank files.
*   A functional `.github/copilot-instructions.md` file demonstrating effective context injection.
*   At least 2-3 example `*.prompt.md` files showcasing task-specific context usage.
*   User guide for setting up and utilizing the system.
*   Demonstrable improvement in Copilot's context awareness for project-specific queries within the repository.
