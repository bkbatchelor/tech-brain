---
name: list-templates
description: "List all available document templates in the TECH-BRAIN '.resources/templates' directory on Google Drive. Use this to help the user choose a format for new or existing notes."
---

# List Templates

This skill identifies and displays all available templates stored in the `TECH-BRAIN` system to assist with document formatting.

## Workflow

1.  **Locate Root**: Find the `TECH-BRAIN` folder.
2.  **Navigate to Templates**: Access `.resources > templates`.
3.  **List Files**: Retrieve the names and IDs of all files in the templates directory.
4.  **Display**: Present the list to the user clearly.

## Technical Details

-   **Templates Folder ID**: `1AAuhEMZz7ljuKj6exDa4jZ1oOqlg6MwZ`
-   **Service**: Google Drive API (`gws drive`)

## Example Command
```bash
gws drive files list --params '{"q": "\"1AAuhEMZz7ljuKj6exDa4jZ1oOqlg6MwZ\" in parents", "fields": "files(id,name,mimeType)"}'
```
