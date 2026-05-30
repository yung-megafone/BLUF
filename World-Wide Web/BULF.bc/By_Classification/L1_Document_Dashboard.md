---
title: "L1_Document_Dashboard"
type: "classification_dashboard"
classification: "L1"
status: "ACTIVE"
record_status: "internal"
indexable: true
tags:
  - BLUF
  - dashboard
  - dataview
  - classification
  - l1
aliases:
  - "L1 Dashboard"
  - "L1 Records"
---

# L1 DOCUMENT DASHBOARD

## Internal Records

> [!info] DYNAMIC DASHBOARD
> This page uses Dataview to display records marked with `classification: "L1"`.

---

# All L1 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  series AS "Series",
  category AS "Category",
  status AS "Status",
  record_status AS "Record Status",
  indexable AS "Indexable"
FROM ""
WHERE classification = "L1"
SORT series ASC, file.name ASC
```

---

# Indexed L1 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  category AS "Category",
  status AS "Status",
  authority AS "Authority"
FROM ""
WHERE classification = "L1"
AND indexable = true
SORT series ASC, file.name ASC
```

---

# Restricted / Non-Indexed L1 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  category AS "Category",
  status AS "Status",
  record_status AS "Record Status",
  compartment AS "Compartment"
FROM ""
WHERE classification = "L1"
AND indexable = false
SORT file.name ASC
```

---

# Recently Updated L1 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  status AS "Status",
  dateformat(file.mtime, "yyyy-MM-dd HH:mm") AS "Updated"
FROM ""
WHERE classification = "L1"
SORT file.mtime DESC
LIMIT 20
```

---

# L1 Records by Category

```dataview
TABLE rows.file.link AS "Documents"
FROM ""
WHERE classification = "L1"
GROUP BY category
SORT category ASC
```

---

# Related Metadata Watch

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  related AS "Related",
  aliases AS "Aliases"
FROM ""
WHERE classification = "L1"
AND (related OR aliases)
SORT file.name ASC
```

---

END OF DASHBOARD
