---
name: markdown-link-migration
description: Move Markdown documentation without breaking internal links
tier: free
---

# Move Markdown documentation without breaking internal links

1. Inventory relative links, reference definitions, image paths and heading anchors before moving files. Skip code blocks and preserve external URLs.
2. Resolve links from each source file and compute replacement targets from its new directory. Confirm anchors using the destination renderer's rules.
3. Return a move map and list of unresolved targets. Test links from nested files and anchors for headings with repeated text.
