#1Parcial #conceptos #redes

```dataview
TASK
FROM "4to Semestre/Redes de Computadoras I"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
GROUP BY regexreplace(file.folder, ".*\/", "")
```
# Significado de Siglas

```dataview
TASK
FROM "4to Semestre/Redes de Computadoras I"
WHERE status = "*"
  AND !completed 
  AND file.name != this.file.name
SORT text ASC
```


