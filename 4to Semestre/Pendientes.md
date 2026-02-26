
```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name
GROUP BY file.link
```
