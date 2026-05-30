---
title: "CONTINUITY_AND_DETERRENCE"
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
  - "Continuity and Deterrence"
---
# CONTINUITY AND DETERRENCE
## Dynamic Strategic Continuity and Final Doctrine Hub

## Continuity-Tagged Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", compartment AS "Compartment", status AS "Status"
FROM ""
WHERE contains(tags, "continuity")
SORT classification DESC, file.name ASC
```

## Warfare Doctrine

```dataview
TABLE WITHOUT ID file.link AS "Doctrine", classification AS "Class", status AS "Status"
FROM ""
WHERE category = "warfare" AND indexable = true
SORT classification DESC, file.name ASC
```

## Strategic Deterrence

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", category AS "Category", related AS "Related"
FROM ""
WHERE contains(tags, "strategic_deterrence") OR contains(tags, "orbital") OR contains(tags, "missile")
SORT classification DESC, file.name ASC
```

## Final / Non-Indexed Continuity Records

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", record_status AS "Record Status", compartment AS "Compartment"
FROM ""
WHERE indexable = false AND (contains(tags, "continuity") OR contains(tags, "final_doctrine") OR classification = "L6")
SORT classification DESC, file.name ASC
```
