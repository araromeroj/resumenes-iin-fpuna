## Pendientes

```sql
```dataview
TASK
FROM "Carpeta"
WHERE !completed and file.name != this.file.name
GROUP BY file.link
```
