---
title: "GRAPH_HUB"
category: hub
classification: L0
status: ACTIVE
record_status: public
indexable: true
tags:
  - BLUF
  - hub
  - dashboard
aliases:
  - "Graph Hub"
---
# GRAPH HUB
## Dynamic Obsidian Navigation Node

> [!info] DYNAMIC HUB
> This page is powered by Dataview. As documents gain metadata, this hub updates automatically.

## Indexed BLUF Records

```dataview
TABLE WITHOUT ID file.link AS "Document", series AS "Series", category AS "Category", classification AS "Class", status AS "Status"
FROM ""
WHERE contains(tags, "BLUF") AND indexable = true AND series
SORT series ASC, file.name ASC
```

## Hidden / Non-Indexed Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", record_status AS "Record Status", compartment AS "Compartment"
FROM ""
WHERE contains(tags, "BLUF") AND indexable = false
SORT classification DESC, file.name ASC
```

## Recently Reviewed

```dataview
TABLE WITHOUT ID file.link AS "Document", last_reviewed AS "Reviewed", classification AS "Class", status AS "Status"
FROM ""
WHERE contains(tags, "BLUF") AND last_reviewed
SORT last_reviewed DESC, file.name ASC
LIMIT 20
```
