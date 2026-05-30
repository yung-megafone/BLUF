---
title: "CLASSIFIED_OPERATIONS_NETWORK"
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
  - "Classified Operations Network"
---
# CLASSIFIED OPERATIONS NETWORK
## Dynamic Restricted Programs and Strategic Operations Hub

> [!warning] ARCHIVAL RESTRICTION NOTICE
> Certain details may be withheld, altered, compartmentalized, or excluded pursuant to [[2105_Classified_Operations_Exemptions]].

## Indexed Classified Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", compartment AS "Compartment", status AS "Status"
FROM ""
WHERE category = "classified" AND indexable = true
SORT classification DESC, file.name ASC
```

## Continuity Black / L5

```dataview
TABLE WITHOUT ID file.link AS "Document", record_status AS "Record Status", related AS "Related"
FROM ""
WHERE classification = "L5"
SORT indexable ASC, file.name ASC
```

## L6 / Nonrecord / Deniable

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", record_status AS "Record Status", compartment AS "Compartment"
FROM ""
WHERE classification = "L6" OR record_status = "nonrecord" OR contains(tags, "deniable")
SORT file.name ASC
```

## NSIC-Linked Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", category AS "Category", compartment AS "Compartment"
FROM ""
WHERE contains(authority, "NSIC") OR contains(tags, "nsic")
SORT classification DESC, file.name ASC
```
