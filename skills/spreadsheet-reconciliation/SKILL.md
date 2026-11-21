---
name: spreadsheet-reconciliation
title: Find What Doesn't Match
description: Compare two spreadsheets and explain missing rows, duplicates, and differences.
tier: free
---

# Reconcile two spreadsheet exports and explain unmatched rows

1. Identify the shared key and expected grain. Preserve identifier strings and leading zeros. Report duplicate keys before joining.
2. Normalize only agreed fields, such as dates and currency. Compare matched values using currency-specific precision and group unmatched records by source.
3. Return counts and amounts before and after matching, plus an exceptions table with source row references.
