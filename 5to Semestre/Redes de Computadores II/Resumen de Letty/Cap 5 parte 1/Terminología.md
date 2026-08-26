## Siglas

```sql
```dataview
TASK
FROM "X Semestre/carpeta"
WHERE status = "*"
SORT file.path ASC
```

## Terminología

```sql
```dataview
TASK
FROM "Carpeta"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
GROUP BY regexreplace(file.folder, ".*\/", "")
```

