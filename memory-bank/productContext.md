# Product Context: Copilot Memory Bank

## Why This Project Exists

GitHub Copilot is powerful, but maintaining deep, structured project context across chat interactions is challenging, often requiring users to repeat information. This project aims to provide Copilot with persistent, structured context to improve its understanding and response relevance within a repository.

## Problems It Solves

*   Reduces the need for users to repeatedly provide project context to Copilot.
*   Enhances Copilot's ability to generate more relevant and accurate code, explanations, and suggestions based on specific project details (architecture, tech stack, goals, progress).
*   Provides a structured way to manage and evolve project knowledge for AI consumption.

## How It Should Work

*   Leverages GitHub Copilot's built-in customization features (`.github/copilot-instructions.md` and potentially `*.prompt.md`).
*   Uses a defined structure within a `memory-bank/` directory (inspired by Cline Memory Bank) to store key project context.
*   The `.github/copilot-instructions.md` file will guide Copilot to utilize the information stored in the `memory-bank/` files.
*   Workflows will be defined for initializing and maintaining this context.
