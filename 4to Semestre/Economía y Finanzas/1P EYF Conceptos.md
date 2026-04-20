
```dataview
TASK
FROM "4to Semestre/Economía y Finanzas"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
GROUP BY regexreplace(file.folder, ".*\/", "")
```

# Siglas importantes

```dataview
TASK
FROM "4to Semestre/Economía y Finanzas"
WHERE status = "*"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
GROUP BY regexreplace(file.folder, ".*\/", "")
```


