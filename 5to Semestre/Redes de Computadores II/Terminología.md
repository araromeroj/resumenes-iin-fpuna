

```dataview
TASK
FROM "5to Semestre/Redes de Computadoras II"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
GROUP BY regexreplace(file.folder, ".*\/", "")
```

# Siglas

```dataview
TASK
FROM "5to Semestre/Redes de Computadoras II"
WHERE status = "*"
SORT file.path ASC
```



