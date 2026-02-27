## Sin Completar
```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = " "
GROUP BY file.folder
```

## Resúmenes Pendientes

```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = "<"
GROUP BY file.folder
```

## Completadas
```dataview
TASK
FROM "4to Semestre"
WHERE completed and file.name != this.file.name
GROUP BY file.folder
```
