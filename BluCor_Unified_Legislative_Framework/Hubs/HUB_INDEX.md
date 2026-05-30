---
title: "HUB_INDEX"
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
  - "Hub Index"
---
# HUB INDEX
## Dynamic BLUF Portal Nodes

- [[GRAPH_HUB]]
- [[CHARTERS_AND_AUTHORITIES]]
- [[PENAL_AND_ENFORCEMENT]]
- [[PUBLIC_COMMUNICATIONS]]
- [[CLASSIFIED_OPERATIONS_NETWORK]]
- [[CONTINUITY_AND_DETERRENCE]]
- [[TREASURY_AND_PROPERTY]]

---

```dataview
TABLE WITHOUT ID file.link AS "Hub", status AS "Status"
FROM ""
WHERE contains(tags, "hub")
SORT file.name ASC
```
