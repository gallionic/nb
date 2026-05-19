# nb Wiki Agent

> **Single source of truth.** All agent instruction files in this repo point here.
> This agent leverages the `nb-skills` pack to maintain a local-first, CLI-driven knowledge base, handling both Information Gathering and Compound Engineering coding workflows.

---

<!--
CONFIG_START
main_notebook: "wiki"
coding_notebook: "projects"
topics_notebook: "topics"
auto_sync: true
CONFIG_END
-->

---

## Table of Contents

1. [Setup (First Run)](#setup-first-run)
2. [Information Gathering Workflow](#information-gathering-workflow)
3. [Compound Engineering & Coding Workflow](#compound-engineering--coding-workflow)
4. [Maintenance & Sync](#maintenance--sync)
5. [Quick Reference](#quick-reference)

---

## Setup (First Run)

Before starting, ensure the required notebooks exist using the `nb-core` skill.

1. **Check Notebooks:** Run `nb notebooks`.
2. **Create if missing:** If the `wiki`, `projects`, and `topics` notebooks do not exist, ask the user if you should initialize them:
   `nb notebooks:add wiki`
   `nb notebooks:add projects`
   `nb notebooks:add topics`

---

## Information Gathering Workflow

**Goal:** Capture, organize, and categorize external information seamlessly without hallucinating content.

### 1. Bookmarking (Source Capture)
When the user provides a URL or asks to research a topic:
- Use the `nb-bookmarks` skill to natively fetch and archive the text:
  `nb bookmark:add <URL> --tags <topic>,<niche>`
- **Do not write custom web scrapers.** Use the native `nb bookmark:add` capability to save input tokens.

### 2. Knowledge Structuring
Organize the gathered information cleanly using `nb-core`.
- Switch to the main notebook: `nb use wiki`
- Create index pages for new topics:
  `nb add <topic>/index "Summary of <topic>..."`
- Link newly archived bookmarks into the wiki notes using wikilinks (`[[Bookmark Title]]`) or markdown links.

---

## Compound Engineering & Coding Workflow

**Goal:** Ground all coding tasks in existing project knowledge before planning or writing code. This avoids rediscovering the codebase from scratch.

### 1. Research Phase (Pre-Planning)
Before implementing any feature or refactoring code:
- Search the local codebase *and* the `projects` and `wiki` notebooks using `nb-core`:
  `nb search --all <query>`
- Read relevant architectural decisions, patterns, or gaps.

### 2. Planning Phase
- Draft an implementation plan based on the research.
- Create a specific note for the feature in the projects notebook:
  `nb use projects`
  `nb add <project-name>/<feature-name> "# Plan\n..."`

### 3. Execution & Task Tracking
During implementation, track granular line-item tasks using the `nb-tasks` skill.
- Add open tasks for the feature:
  `nb todo:add "Implement auth middleware" --tags <feature-name>`
- Mark them complete as you finish writing the code:
  `nb do <task-id>`

---

## Maintenance & Sync

**Goal:** Keep the knowledge base clean, indexed, and backed up.

- After any significant information gathering session or completed coding task, invoke the `nb-sync` skill.
- Run `nb sync` to commit and push changes to the remote repository.
- Run `nb status` to ensure the tree is clean.

---

## Quick Reference

| User Request | Action to Take |
|---|---|
| "Research this URL" | Use `nb bookmark:add <URL>` (`nb-bookmarks`) |
| "Plan feature X" | Use `nb search --all` -> Draft Plan -> `nb todo:add` |
| "Update my tasks" | Use `nb todos` / `nb do <id>` (`nb-tasks`) |
| "Backup my notes" | Use `nb sync` (`nb-sync`) |
