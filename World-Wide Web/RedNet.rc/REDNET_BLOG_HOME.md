---
title: "REDNET_BLOG_HOME"
type: "civilian_blog_home"
classification: "UNOFFICIAL"
status: "ACTIVE"

tags:
  - rednet
  - civilian
  - blog
  - resistance
  - archive
  - dashboard

aliases:
  - "RedNet Home"
  - "RedNet Blog"
  - "Resistance Archive Home"

domain:
  - "RedNet.rc"

indexable: true
---

# URGENT / FEATURED

```dataview
TABLE WITHOUT ID
  file.link AS "Post",
  status AS "Status",
  classification AS "Class",
  dateformat(file.mtime, "yyyy-MM-dd") AS "Updated"
FROM ""
WHERE contains(tags, "rednet")
AND (
  contains(tags, "leak")
  OR contains(tags, "hellmarch")
  OR contains(tags, "urgent")
)
SORT file.mtime DESC
LIMIT 5
```

---

# Latest RedNet Posts

```dataview
TABLE WITHOUT ID
  file.link AS "Post",
  type AS "Type",
  classification AS "Class",
  status AS "Status",
  dateformat(file.mtime, "yyyy-MM-dd") AS "Updated"
FROM ""
WHERE contains(tags, "rednet")
AND file.name != this.file.name
SORT file.mtime DESC
LIMIT 20
```

---

# Archive Analysis

```dataview
TABLE WITHOUT ID
  file.link AS "Article",
  aliases AS "Also Known As",
  status AS "Status"
FROM ""
WHERE contains(tags, "rednet")
AND contains(tags, "analysis")
SORT file.name ASC
```

---

# Leaks / Dispatches

```dataview
TABLE WITHOUT ID
  file.link AS "Leak",
  classification AS "Class",
  status AS "Status",
  aliases AS "Aliases"
FROM ""
WHERE contains(tags, "rednet")
AND (
  contains(tags, "leak")
  OR contains(tags, "dispatch")
  OR contains(tags, "resistance")
)
SORT file.mtime DESC
```

---

# Continuity Black Watchlist

```dataview
TABLE WITHOUT ID
  file.link AS "Record",
  type AS "Type",
  status AS "Status",
  aliases AS "Aliases"
FROM ""
WHERE contains(tags, "rednet")
AND (
  contains(tags, "continuity_black")
  OR contains(tags, "cno")
  OR contains(tags, "sap")
  OR contains(tags, "classification")
)
SORT file.mtime DESC
```

---

# Known Public Classification Levels

|Classification|Public Understanding|
|---|---|
|`L0`|Public-release records|
|`L1`|Internal government records|
|`L2`|Strategic restricted doctrine|
|`L5`|Continuity Black / SAP-tier compartmentalization|
|`L6`|Alleged nonrecord authority hidden from normal systems|
|`???`|Rumored additional levels|

---

# RedNet Index by Tag

```dataview
TABLE WITHOUT ID
  file.link AS "Post",
  tags AS "Tags"
FROM ""
WHERE contains(tags, "rednet")
AND file.name != this.file.name
SORT file.name ASC
```

---

> [!quote]  
> Some records are missing because they were never meant to exist.

---

END OF REDNET HOME