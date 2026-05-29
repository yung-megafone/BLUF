# Continuity Black Dashboard

> The archive contains records the archive denies containing.

```dataview
TABLE classification, record_status, compartment
FROM ""
WHERE contains(record_status, "null")
SORT classification DESC
```

---

## Hidden / Nonrecord Programs

```dataview
TABLE classification, record_status
FROM ""
WHERE indexable = false AND record_status != "null"
SORT file.name ASC
```