---
title: "CLASSIFICATION_DASHBOARD_INDEX"
type: "classification_dashboard_index"
classification: "L0"
status: "ACTIVE"
record_status: "public"
indexable: true
tags:
  - BLUF
  - dashboard
  - dataview
  - classification
  - index
aliases:
  - "Classification Dashboard Index"
  - "Clearance Dashboard Index"
---

# CLASSIFICATION DASHBOARD INDEX

## Dynamic BLUF Classification Portal

- [[L1_Document_Dashboard]]
- [[L2_Document_Dashboard]]
- [[L3_Document_Dashboard]]
- [[L4_Document_Dashboard]]
- [[L5_Document_Dashboard]]
- [[L6_Document_Dashboard]]

---

# Classification Count

```dataview
TABLE length(rows) AS "Records"
FROM ""
WHERE classification
GROUP BY classification
SORT classification ASC
```

---

# All Restricted / Non-Indexed Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  classification AS "Class",
  category AS "Category",
  status AS "Status",
  record_status AS "Record Status",
  compartment AS "Compartment"
FROM ""
WHERE indexable = false
SORT classification DESC, file.name ASC
```

---

# Sealed / Nonexistent / Deniable Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  classification AS "Class",
  status AS "Status",
  record_status AS "Record Status",
  compartment AS "Compartment"
FROM ""
WHERE record_status = "sealed"
OR record_status = "nonexistent"
OR record_status = "nonrecord"
OR contains(tags, "deniable")
SORT classification DESC, file.name ASC
```

---

# Continuity Black / CNO / SAP Watchlist

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  classification AS "Class",
  status AS "Status",
  compartment AS "Compartment"
FROM ""
WHERE contains(tags, "continuity_black")
OR contains(tags, "sap")
OR contains(tags, "cno")
OR compartment
SORT classification DESC, file.name ASC
```

---

END OF INDEX
