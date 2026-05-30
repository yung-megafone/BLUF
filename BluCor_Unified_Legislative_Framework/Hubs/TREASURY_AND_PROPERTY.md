---
title: "TREASURY_AND_PROPERTY"
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
  - "Treasury and Property"
---
# TREASURY AND PROPERTY
## Dynamic Economic, Property, Reserve, and Conversion Hub

## Treasury Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", status AS "Status", issued AS "Issued"
FROM ""
WHERE contains(tags, "treasury") OR contains(authority, "Treasury Authority")
SORT series ASC, file.name ASC
```

## Conversion / Taxation / Reserve Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", historical_status AS "Historical Status", status AS "Status"
FROM ""
WHERE contains(tags, "conversion") OR contains(tags, "taxation") OR contains(tags, "reserve_bank") OR contains(tags, "finance")
SORT issued ASC, file.name ASC
```

## Property and Acquisition Records

```dataview
TABLE WITHOUT ID file.link AS "Document", status AS "Status", authority AS "Authority"
FROM ""
WHERE contains(tags, "property") OR contains(tags, "bill_of_sale") OR contains(tags, "contractual")
SORT file.name ASC
```

## Legacy / Superseded Treasury Records

```dataview
TABLE WITHOUT ID file.link AS "Document", status AS "Status", historical_status AS "Historical Status", superseded_by AS "Superseded By"
FROM ""
WHERE contains(tags, "legacy") OR status = "DEPRECATED" OR historical_status = "LEGACY"
SORT issued ASC
```
