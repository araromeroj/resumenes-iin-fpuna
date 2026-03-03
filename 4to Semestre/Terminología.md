```dataview
TASK
FROM "4to Semestre"
WHERE status = "I"
  AND !completed 
  AND file.name != this.file.name
GROUP BY regexreplace(file.folder, ".*\/", "")
```
