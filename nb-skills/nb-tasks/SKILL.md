---
name: nb-tasks
description: Interact directly with nb's built-in line-item task runner and todo architecture via the CLI. Use when you need to manage, complete, or review tasks and to-do items.
---

# nb Tasks Skill

Use the `nb` CLI to manage tasks and to-do lists efficiently. `nb` has a built-in line-item task runner.

## Managing Todos
- `nb todos` - List all open tasks across notes.
- `nb todo:add <task description>` - Add a new standalone task.
- `nb todo:add <task description> --tags <tag>` - Add a task with a specific tag.
- `nb do <id>` - Mark a task as complete.
- `nb undo <id>` - Mark a completed task as incomplete.

## Viewing Tasks
- `nb done` - List all completed tasks.
- `nb todos --all` - List both open and completed tasks.
- `nb search --todos <query>` - Search specifically within task descriptions.

Integrating tasks directly into notes allows for context-rich to-do lists, manageable natively from the CLI.
