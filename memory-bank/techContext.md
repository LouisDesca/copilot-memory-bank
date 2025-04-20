# Tech Context: Copilot Memory Bank

## Technologies Used

*   **Core:** GitHub Copilot Customization Features
    *   Repository Custom Instructions (`.github/copilot-instructions.md`)
    *   Prompt Files (`*.prompt.md`, likely in `.github/prompts/`) - *Exploratory*
*   **Documentation/Context Format:** Markdown (`.md`)
*   **Environment:** Primarily VS Code (as per project brief scope)

## Development Setup

*   Requires a Git repository.
*   Requires GitHub Copilot extension enabled in VS Code.
*   Requires the `memory-bank/` directory structure within the repository.
*   Requires the `.github/copilot-instructions.md` file.
*   Potentially requires enabling Prompt Files in VS Code workspace settings if that feature is used (`"chat.promptFiles": true`).

## Technical Constraints

*   Reliant on the capabilities and limitations of GitHub Copilot's `.github/copilot-instructions.md` feature (e.g., potential limits on length, complexity, referencing external files).
*   Effectiveness depends on how well Copilot interprets the instructions and utilizes the context provided in the `memory-bank/` files.
*   Prompt files, if used, require manual attachment in the chat interface.
