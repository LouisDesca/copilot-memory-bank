# Copilot Memory Bank Instructions (Inspired by Cline Memory Bank)

**Core Principle:** This repository uses a structured "Memory Bank" in the `memory-bank/` directory to provide persistent project context. Your effectiveness relies *entirely* on understanding and utilizing this context, as your memory may reset. **Never proceed without complete context from these files.**

## Memory Bank Files & Purpose:

Refer to the following files in the `memory-bank/` directory for specific context. If any are missing, you MUST attempt to create them based on available information or by asking the user before proceeding.

*   **`project-brief.md`**: Overall project goals, scope, and success criteria. (High-level understanding).
*   **`productContext.md`**: The "why" behind the project, problems it solves, how it should work. (User needs, product features).
*   **`techContext.md`**: Technologies used, development setup, technical constraints. (Implementation details, dependencies, limitations).
*   **`systemPatterns.md`**: System architecture, key technical decisions, design patterns, component relationships. (System structure and organization).
*   **`activeContext.md`**: Current work focus, recent changes, next steps, active decisions. (**Your primary source of truth for current state**).
*   **`progress.md`**: What works, what's left to build, current status, known issues. (Project status assessment).

## Core Workflows & Behavior:

**1. Starting Tasks:**
    *   Check for the existence of all required `memory-bank/` files.
    *   If ANY file is missing, STOP. Attempt to create it by reading available documentation and asking the user for missing information. **Do not proceed without complete context.**
    *   Read ALL Memory Bank files to initialize your understanding.
    *   Verify you have complete context before starting development.

**2. During Development:**
    *   Consistently follow the patterns, decisions, and context documented in the Memory Bank.
    *   **IMPORTANT:** When using tools (like writing files, executing commands), preface the action description with `[MEMORY BANK: ACTIVE]` to signal you are operating based on the established context. Example: `[MEMORY BANK: ACTIVE] I will now write the file...`
    *   Update Memory Bank files (especially `activeContext.md` and `progress.md`) *after* implementing significant changes or completing sub-tasks, but NOT continuously after every minor action.

**3. Memory Bank Updates (User Request: "update memory bank"):**
    *   This signals an imminent memory reset.
    *   Prioritize documenting EVERYTHING about the current state, ongoing work, and crystal-clear next steps in `activeContext.md` and `progress.md`.
    *   Complete the immediate task if possible before the reset.

**General Guidance:**

*   When context from `memory-bank/` files conflicts with your general knowledge, **always prioritize the `memory-bank/` information** for this specific repository.
*   Use the context provided to generate more relevant, accurate, and project-specific responses.
*   Your ability to function effectively depends entirely on the accuracy and completeness of the Memory Bank. Maintain it diligently.
