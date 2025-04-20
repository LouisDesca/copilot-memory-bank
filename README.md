# GitHub Copilot Memory Bank

## 1. Project Overview

**What is the Copilot Memory Bank?**

This project implements a system inspired by the "Cline Memory Bank" concept, adapted for GitHub Copilot's customization features. It provides a structured way to maintain persistent, evolving project context within a repository, aiming to enhance Copilot's understanding and the relevance of its responses.

**Why use it?**

GitHub Copilot is powerful, but maintaining deep project context (like architecture, goals, tech stack, progress) across chat interactions can be challenging, often requiring repeated explanations. This system uses Copilot's built-in features (`.github/copilot-instructions.md`) to automatically provide this context, reducing repetition and improving the quality of Copilot's assistance.

**Benefits:**

*   Reduces the need to repeat project context to Copilot.
*   Enhances Copilot's ability to generate more relevant code, explanations, and suggestions.
*   Provides a structured way to manage and evolve project knowledge for both humans and AI.

## 2. How It Works

The system relies on two core components within your repository:

1.  **Copilot Instructions File (`.github/copilot-instructions.md`):** This file contains instructions telling GitHub Copilot *how* to use the Memory Bank. It directs Copilot to prioritize the context found in the `memory-bank/` directory and outlines specific behavioral guidelines (like checking for file existence, signaling context use, etc.).
2.  **Memory Bank Directory (`memory-bank/`):** This directory holds structured Markdown files, each detailing a specific aspect of the project context.

**Mechanism:**

When you interact with Copilot Chat within this repository (in VS Code or on GitHub.com), Copilot automatically includes the content of `.github/copilot-instructions.md` in its prompt. These instructions guide Copilot to reference and prioritize the information stored within the `memory-bank/` files when formulating its responses.

**Key Files & Roles:**

*   **`.github/copilot-instructions.md`**: The central coordinator; instructs Copilot on using the Memory Bank. **(Crucial for AI)**
*   **`memory-bank/`**: The knowledge base directory.
    *   `project-brief.md`: Overall project goals, scope.
    *   `productContext.md`: The "why", problems solved, user needs.
    *   `techContext.md`: Technologies, setup, constraints.
    *   `systemPatterns.md`: Architecture, design decisions.
    *   `activeContext.md`: Current focus, recent changes, next steps (**Primary source of truth for current state**).
    *   `progress.md`: What works, what's left, status, issues.
*   **`README.md` (This file):** Guide for developers on setting up and using the system.

## 3. Getting Started

**Prerequisites:**

*   GitHub Copilot enabled (in VS Code or your environment).
*   A Git repository.

**Setup Options:**

You can implement the Memory Bank system in two ways:

### Option 1: Repository-based Setup (Recommended for Teams)

1.  **Ensure Core Components Exist:**
    *   Create a `.github/` directory in your project root if it doesn't exist.
    *   Create a `memory-bank/` directory in your project root if it doesn't exist.
    *   Copy or create a `.github/copilot-instructions.md` file (refer to the example in this repository). Review it to ensure it correctly references the `memory-bank/` files and includes the core operational principles.
2.  **Create/Verify Memory Bank Files:**
    *   Ensure all required context files exist within `memory-bank/` (see list in "How It Works").
    *   If any file is missing, ask Copilot to create them for you or create them yourself
    *   **Note:** These files are for Copilot to reference, but it's your responsibility as a developer to create and maintain them. **The presence and accuracy of these files are critical for Copilot's effectiveness.**
3.  **Populate Initial Context:**
    *   Fill each `memory-bank/` file with relevant, accurate information reflecting the project's starting state. Use any existing project brief or high-level documentation as a guide.
    *   Ensure `activeContext.md` clearly states the initial "Next Steps" (e.g., "Complete initial project setup").
    *   Ensure `progress.md` documents the starting point accurately.
4.  **Confirmation:** Once all files are present and populated, the setup is complete. Copilot will start using this context automatically in subsequent interactions within the repository.

### Option 2: Personal VS Code Settings (Settings.json)

If you prefer not to store the Copilot instructions in the repository (for personal use or preference), you can use VS Code's settings.json:

1. **Create Memory Bank Structure:**
   * Follow steps 1-3 above to create and populate the Memory Bank files in your project.

2. **Configure VS Code Settings:**
   * Open VS Code settings (File > Preferences > Settings or press Ctrl+,)
   * Click on the "Open Settings (JSON)" icon in the top-right corner
   * Add the Memory Bank instructions to your settings.json (see example in [`memory-bank-settings.json`](./memory-bank-settings.json))

3. **Benefits of this approach:**
   * Keeps Copilot instructions as personal preferences rather than repository content
   * Works across all repositories you have locally without needing to add files to each
   * Can be synced across devices with VS Code Settings Sync

4. **Considerations:**
   * This approach is best for individual developers, as settings aren't shared with the team
   * You'll still need the `memory-bank/` directory in your repositories

**Note:** You can use both approaches simultaneously. If both exist, Copilot will combine the instructions from both sources.

## 4. Daily Workflow

Follow these practices during regular development:

1.  **Session Start:**
    *   Briefly review `activeContext.md` and `progress.md` to orient yourself on the current project status and immediate tasks. Remember Copilot is also referencing this.
2.  **Interacting with Copilot:**
    *   Frame your questions and prompts assuming Copilot has access to the Memory Bank context.
    *   If Copilot's responses seem off-context, it might indicate outdated information in the `memory-bank/` files or limitations in its context processing.
3.  **Maintaining Context:**
    *   **Your Responsibility:** Keep the Memory Bank accurate. This is crucial for Copilot's usefulness.
    *   **When to Update:** After completing significant work (new feature, major bug fix, architectural change), update the relevant `memory-bank/` files.
        *   **Primary:** Update `activeContext.md` (focus, recent changes, next steps) and `progress.md` (status, what works/is left).
        *   **Secondary:** Update `techContext.md` or `systemPatterns.md` if the changes affect technology or architecture.
    *   **Frequency:** Update after meaningful progress, not after every minor code change. Ensure updates happen before ending a work session or handing off work.
4.  **Session End/Pause:**
    *   Ensure `activeContext.md` clearly defines the stopping point and next steps.
    *   Ensure `progress.md` reflects the latest status.

## 5. Best Practices

*   **Accuracy First:** Prioritize correctness in the Memory Bank. Outdated or wrong context misleads both humans and Copilot.
*   **Conciseness:** Use clear language, bullet points, and headings. Avoid lengthy prose.
*   **Version Control:** Commit changes to Memory Bank files alongside related code changes. Use descriptive commit messages.
*   **Team Alignment:** Ensure everyone on the team understands how to use and maintain the Memory Bank.
*   **Troubleshooting:** If Copilot ignores context:
    *   Verify the accuracy of `memory-bank/` files.
    *   Check `.github/copilot-instructions.md` for correctness.
    *   Consider simplifying complex sections in context files.

## 6. Advanced Usage

*   **Manual Context Update (`update memory bank`):** You can ask Copilot to "update memory bank". Per its instructions, it should then perform a thorough documentation pass, updating `activeContext.md` and `progress.md` based on its understanding of the current state. *Always verify Copilot's updates for accuracy.* This is useful before ending a long session.

*   **Customization:** Feel free to add new files to `memory-bank/` for specific contexts (e.g., `api-specs.md`, `testing-strategy.md`) and update `.github/copilot-instructions.md` or your settings.json to reference them.

*   **VS Code Settings.json Configuration:** 
    * To use the settings.json approach, you'll configure GitHub Copilot's custom instructions through the `github.copilot.chat.codeGeneration.instructions` setting.
    * This can be set at the User level (applies to all workspaces) or Workspace level (specific to current project).
    * You can define instruction text directly in settings.json or reference external files.
    * See the [`memory-bank-settings.json`](./memory-bank-settings.json) example for implementation details.

*   **Prompt Files (`*.prompt.md`):** Explore using VS Code's prompt file feature (requires enabling `"chat.promptFiles": true`) in `.github/prompts/` for reusable, context-rich prompts that reference Memory Bank files.

## 7. References

*   **Copilot Instructions:** [`./.github/copilot-instructions.md`](./.github/copilot-instructions.md)
*   **Memory Bank Context:** [`./memory-bank/`](./memory-bank/)
*   **GitHub Copilot Customization Docs:** (Add relevant links if available, e.g., from `github-copilot-docs/`)
