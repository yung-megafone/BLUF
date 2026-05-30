---
title: "CHARTERS_AND_AUTHORITIES"
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
  - "Charters and Authorities"
---
# CHARTERS AND AUTHORITIES
## Dynamic Coalition Governance Hub

## Governmental Charters

```dataview
TABLE WITHOUT ID file.link AS "Charter", classification AS "Class", authority AS "Authority", status AS "Status"
FROM ""
WHERE contains(tags, "charter") AND indexable = true
SORT series ASC, file.name ASC
```

## Foundational Authority

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", status AS "Status"
FROM ""
WHERE category = "foundational" AND indexable = true
SORT file.name ASC
```

## Agency Authority Records

```dataview
TABLE WITHOUT ID file.link AS "Document", authority AS "Authority", classification AS "Class", status AS "Status"
FROM ""
WHERE category = "governmental" AND indexable = true
SORT classification DESC, file.name ASC
```

## BluCor-Linked Authority

```dataview
TABLE WITHOUT ID file.link AS "Document", classification AS "Class", category AS "Category"
FROM ""
WHERE contains(authority, "BluCor") AND indexable = true
SORT series ASC, file.name ASC
```

## Related Hubs

- [[PENAL_AND_ENFORCEMENT]]
- [[PUBLIC_COMMUNICATIONS]]
- [[CLASSIFIED_OPERATIONS_NETWORK]]
- [[CONTINUITY_AND_DETERRENCE]]
