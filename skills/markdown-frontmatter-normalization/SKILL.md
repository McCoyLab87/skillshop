---
name: markdown-frontmatter-normalization
title: Clean Up Your Markdown File Details
description: Make the titles, tags, and other details at the top of your files consistent.
tier: free
---

# Normalize Markdown metadata while preserving document bodies

1. Inventory field names, types and missing values. Define the canonical schema and pick migration rules for aliases and conflicting values.
2. Update only frontmatter and preserve the body bytes where possible. Keep unknown fields unless explicitly deprecated and flag duplicate identifiers.
3. Return the schema, a dry-run diff and a validation summary. Check that a second run produces no changes.
