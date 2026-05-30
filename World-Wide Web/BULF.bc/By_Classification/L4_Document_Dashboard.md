---
title: "L4_Document_Dashboard"
type: "classification_dashboard"
classification: "L4"
status: "ACTIVE"
record_status: "internal"
indexable: true
tags:
  - BLUF
  - dashboard
  - dataview
  - classification
  - l4
aliases:
  - "L4 Dashboard"
  - "L4 Records"
---

# L4 DOCUMENT DASHBOARD

## Internal Security Records

> [!info] DYNAMIC DASHBOARD
> This page uses Dataview to display records marked with `classification: "L4"`.

---

# All L4 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  series AS "Series",
  category AS "Category",
  status AS "Status",
  record_status AS "Record Status",
  indexable AS "Indexable"
FROM ""
WHERE classification = "L4"
SORT series ASC, file.name ASC
```

---

# Indexed L4 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  category AS "Category",
  status AS "Status",
  authority AS "Authority"
FROM ""
WHERE classification = "L4"
AND indexable = true
SORT series ASC, file.name ASC
```

---

# Restricted / Non-Indexed L4 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  category AS "Category",
  status AS "Status",
  record_status AS "Record Status",
  compartment AS "Compartment"
FROM ""
WHERE classification = "L4"
AND indexable = false
SORT file.name ASC
```

---

# Recently Updated L4 Records

```dataview
TABLE WITHOUT ID
  file.link AS "Document",
  status AS "Status",
  dateformat(file.mtime, "yyyy-MM-dd HH:mm") AS "Updated"
FROM ""
WHERE classification = "L4"
SORT file.mtime DESC
LIMIT 20
```

---

# L4 Records by Category

```dataview
TABLE rows.file.link AS "Documents"
FROM ""
WHERE classification = "L4"
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
WHERE classification = "L4"
AND (related OR aliases)
SORT file.name ASC
```

---

END OF DASHBOARD
