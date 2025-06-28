# Changelog Prompt

## Overview
This provides instructions for the AI agents to maintain a document of changelogs as a single document `changelog.md` in the root of the repository.

## Instructions
1. The AI agent should maintain a document of changelogs as a single document `changelog.md` in the root of the repository.
2. Each time a change is made to the repository, the AI agent should add a new section to the `changelog.md` file.
3. The AI agent should use the following format for each section:
    ```markdown
    ## Version X.Y.Z - YYYY-MM-DD
    ### Changes
    - Change 1
    - Change 2
    - Change 3
    ```
4. The AI agent should update the `version` field in the `package.json` file to reflect the new version number.
5. The AI agent should create a new git tag for the new version number. 
6. The AI agent should update the `CHANGELOG` section in the `README.md` file to reflect the new version number and link to the new section in the `changelog.md` file.
