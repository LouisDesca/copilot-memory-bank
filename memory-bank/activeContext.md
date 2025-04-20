# Active Context: Copilot Memory Bank

## Current Work Focus

*   System is fully operational with recent refinements to Copilot instructions.
*   Apache 2.0 license compliance (as a derivative/fork) is in place.
*   LICENSE and NOTICE files are present in the root directory for compliance with the upstream license.
*   The `README.md` now provides a comprehensive guide for developers.
*   The `.github/copilot-instructions.md` file has been refined to improve Copilot's context handling behavior.
*   Current focus: Testing the Memory Bank system in real development scenarios with the improved instructions.
*   Added support for VS Code settings.json as an alternative to repository-based copilot-instructions.
*   Potentially creating example `*.prompt.md` files.

## Recent Changes

*   Updated `.github/copilot-instructions.md` to specify that Copilot should read memory bank files at the beginning of each new chat session, not for every request within a session.
*   Updated README.md to clarify that memory bank file creation/verification instructions are for human developers, not for Copilot.
*   Enhanced README.md with two new sections explaining how to use settings.json as an alternative to repository-based instructions.
*   Created a `memory-bank-settings.json` template file to help developers implement the Memory Bank using VS Code settings.
*   LICENSE file with full Apache 2.0 license text added for compliance with upstream (not as a re-licensing).
*   Empty NOTICE file created in the root directory for compliance.
*   Updated `memory-bank/projectbrief.md` and `.clinerules` to clarify compliance-only status.
*   Created and refined all core Memory Bank files.
*   Created and then transformed workflow documentation into a developer-focused `README.md` in the project root.

## Next Steps

1.  Continue testing the Copilot Memory Bank system with the refined instructions to validate their effectiveness.
2.  Monitor how well Copilot follows the updated instructions regarding when to read memory bank files.
3.  Evaluate how well the settings.json approach works compared to the repository-based approach.
4.  Create example `*.prompt.md` files if advanced prompt workflows are needed.
5.  Continue to keep `activeContext.md` and `progress.md` up to date after significant changes.

## Active Decisions & Considerations

*   Determining the optimal balance between comprehensive context and instruction efficiency.
*   Evaluating the effectiveness of the new instructions in real-world usage scenarios.
*   Assessing if the settings.json approach provides adequate flexibility for developers who don't want to store instructions in their repositories.
*   When and how to introduce prompt files for advanced use cases.
*   Ensuring all team members understand and follow the updated documentation.
