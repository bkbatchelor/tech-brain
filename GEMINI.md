# Tech Second Brain Workspace

## Directory Overview
This directory serves as the local operational workspace and toolset for the `TECH-BRAIN`, a structured knowledge management system. Its primary purpose is to provide the automation and guidelines needed to process, standardize, tag, and organize raw files and notes imported from a Google Drive `00_inbox` into a structured Second Brain hierarchy (e.g., `01_projects`, `02_areas`, `03_resources`, `04_archives`).

## Key Files & Assets
The core logic of this workspace is encapsulated within the custom Gemini skills and their associated assets:

*   **.gemini/skills/tech-brain/SKILL.md**: The foundational instruction set and workflow rules for the repository. It enforces template usage, directory structure maintenance, and mandatory front-matter/tagging conventions for all incoming documents.
*   **.gemini/skills/tech-brain/assets/front_matter_template.md**: The required Markdown front-matter template that must be applied to all processed documents.
*   **.gemini/skills/tech-brain/assets/tags_schema.json**: The authoritative JSON schema defining allowed tags and categories for the knowledge base.
*   **.gemini/skills/tech-brain/scripts/** (`validate.py`, `list_documents.py`): Python utility scripts designed for validating document formats and managing the catalog of contents.
*   **.gemini/skills/tech-brain/references/**: Contains reference guidelines and execution details for custom agent commands (`process-inbox`, `show-toc`, `validate-note`).

## Usage
This workspace is designed to be operated interactively via Gemini CLI using the `tech-brain` skill. The repository automates the ingestion and standardization of notes. 

Key workflows are triggered using the following custom commands:
*   `process-inbox`: Scans the designated Google Drive `00_inbox`, applies mandatory templates and front-matter to new files, and automatically routes them to their appropriate structured folders (`01_projects`, `02_areas`, etc.).
*   `validate-note`: Checks existing documents to ensure they strictly comply with the `tags_schema.json` and required front-matter formatting rules.
*   `show-toc`: Generates or displays a comprehensive table of contents for the current state of the knowledge base.

**Important Constraints:** All files processed through this workspace must strictly adhere to the front-matter templates. MUST explicitly excluded from automated processing any folder that is prefixed with an underscore (`_`) or matches `.Trash*`.

## Maintenance
*   **Cleanup:** Always clean up temporary files & folders that were created during the task execution to maintain a clean workspace.