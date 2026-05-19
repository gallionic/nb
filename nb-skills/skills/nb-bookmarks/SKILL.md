---
name: nb-bookmarks
description: Archive raw web text and log documentation using nb's native bookmarking functionality. Use this to efficiently save URLs and their content without wasting input tokens.
---

# nb Bookmarks Skill

Use the `nb` CLI tool to natively archive web text, save URLs, and log documentation efficiently.

## Adding Bookmarks
- Natively archive a URL and fetch its content:
  ```bash
  nb bookmark:add <URL>
  ```
- Add a bookmark with specific tags:
  ```bash
  nb bookmark:add <URL> --tags <tag1>,<tag2>
  ```
- Specify a custom title for the bookmark:
  ```bash
  nb bookmark:add <URL> --title "My Custom Title"
  ```

## Working with Bookmarks
- `nb bookmarks` - List all saved bookmarks in the active notebook.
- `nb show <bookmark_id>` - Display the cached markdown content of the bookmarked URL.
- `nb search --bookmarks <query>` - Search specifically within cached bookmarks.

Using native bookmarking helps avoid wasting input tokens on manual web-to-markdown extraction scripts.
