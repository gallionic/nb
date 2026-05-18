---
name: nb-core
description: Navigate notebooks, create/read/edit notes using standard sub-notebook paths, and leverage nb search with regex filtering. Use when interacting with nb notes.
---

# nb Core Skill

Use the `nb` CLI tool to create, read, edit, and search text notes natively without writing custom scripts.

## Notebook Navigation
- `nb notebooks` - List all notebooks.
- `nb use <notebook>` - Switch to a specific notebook.
- `nb ls` - List contents of the current notebook.

## Note Operations
- `nb add <title> [content]` - Create a new note. You can also specify sub-notebook paths: `nb add folder/subfolder/title`.
- `nb edit <id|title>` - Open a note in the configured editor (use CLI automation like sed or standard editing tools if interactive editor blocks).
- `nb show <id|title>` - Print note contents to the terminal.
- `nb delete <id|title>` - Remove a note.

## Search
Do not write custom Python scripts to search. Use the native `nb search` command with regex filtering.
- `nb search <query>` - Search for text across the active notebook.
- `nb search --all <query>` - Search across all notebooks.
- `nb search --regex "<pattern>"` - Use regular expressions for complex searches.
