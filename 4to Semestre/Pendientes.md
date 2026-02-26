## Sin Completar
```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = " "
GROUP BY file.link
```

## Resúmenes Pendientes

```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = "<"
GROUP BY file.link
```

## Completadas
```dataview
TASK
FROM "4to Semestre"
WHERE completed and file.name != this.file.name
GROUP BY file.link
```
