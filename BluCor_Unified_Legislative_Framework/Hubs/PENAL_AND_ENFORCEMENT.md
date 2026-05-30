---
title: "PENAL_AND_ENFORCEMENT"
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
  - "Penal and Enforcement"
---
# PENAL AND ENFORCEMENT
## Dynamic Penal Doctrine and Security Hub

## Penal Doctrine

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", status AS "Status"
FROM ""
WHERE category = "penal" AND indexable = true
SORT file.name ASC
```

## BWARS Enforcement Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", category AS "Category", status AS "Status"
FROM ""
WHERE contains(authority, "BWARS") OR contains(tags, "bwars")
SORT classification DESC, file.name ASC
```

## Treason / Tribunal / Economic Enforcement

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", tags AS "Tags"
FROM ""
WHERE contains(tags, "treason") OR contains(tags, "tribunal") OR contains(tags, "economic") OR contains(tags, "criminal_code")
SORT classification DESC, file.name ASC
```

## Related Hubs

- [[CHARTERS_AND_AUTHORITIES]]
- [[CLASSIFIED_OPERATIONS_NETWORK]]
- [[PUBLIC_COMMUNICATIONS]]
