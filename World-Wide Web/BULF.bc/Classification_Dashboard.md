# Classification Dashboard

## Public Release (L0)

```dataview
TABLE status, category
FROM ""
WHERE classification = "L0"
SORT file.name ASC
```

---

## Internal / Restricted (L1-L2)

```dataview
TABLE classification, status
FROM ""
WHERE classification = "L1"
OR classification = "L2"
SORT classification ASC
```

---

## Strategic / Intelligence (L3-L4)

```dataview
TABLE classification, compartment
FROM ""
WHERE classification = "L3"
OR classification = "L4"
SORT classification ASC
```

---

## Continuity Black (L5)

```dataview
TABLE classification, compartment
FROM ""
WHERE classification = "L5"
SORT file.name ASC
```

---

## Nonrecord / Deniable (L6)

```dataview
TABLE classification, record_status
FROM ""
WHERE classification = "L6"
OR record_status = "nonrecord"
SORT file.name ASC
```