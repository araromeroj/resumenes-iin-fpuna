
```dataview
TASK
FROM "_Archivo Académico/4to Semestre"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
SORT split(file.folder, "/")[3] ASC
GROUP BY split(file.folder, "/")[2]
SORT key ASC
```
 