---
title: "PUBLIC_COMMUNICATIONS"
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
  - "Public Communications"
---
# PUBLIC COMMUNICATIONS
## Dynamic Public Affairs and Narrative-Control Hub

## Public Affairs Releases

```dataview
TABLE WITHOUT ID file.link AS "Public Record", status AS "Status", issued AS "Issued", tags AS "Tags"
FROM ""
WHERE category = "public_affairs" AND indexable = true
SORT issued DESC, file.name ASC
```

## L0 Public Records Across All Series

```dataview
TABLE WITHOUT ID file.link AS "Document", category AS "Category", status AS "Status"
FROM ""
WHERE classification = "L0" AND indexable = true
SORT series ASC, file.name ASC
```

## Declassified Records

```dataview
TABLE WITHOUT ID file.link AS "Document", historical_classification AS "Former Class", declassified_to AS "Current Class", status AS "Status"
FROM ""
WHERE status = "DECLASSIFIED" OR contains(tags, "declassified")
SORT file.name ASC
```

## Public Records With Classified Counterparts

```dataview
TABLE WITHOUT ID file.link AS "Public Record", related AS "Related Records"
FROM ""
WHERE category = "public_affairs" AND related
SORT file.name ASC
```
