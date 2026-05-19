---
name: nb-sync
description: Call nb sync to automatically trigger underlying Git synchronization and tracking. Use to ensure notebooks are backed up and synchronized after major changes.
---

# nb Sync Skill

Use the `nb` CLI's built-in Git synchronization capabilities to track changes and backup notebooks without needing to run manual git commands inside notebook directories.

## Synchronization Commands
- `nb sync` - Automatically add, commit, and push changes to the configured remote repository, and pull any new changes.
- `nb status` - View the current Git status of the notebook repository.

## Important Note
`nb` handles version control automatically for many operations if `NB_AUTO_SYNC` is enabled, but calling `nb sync` directly is best practice after cataloging information, doing batch edits, or completing tasks to ensure immediate synchronization with the remote backend.
