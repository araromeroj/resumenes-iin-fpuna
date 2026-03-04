## Sin Completar
```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = " "
GROUP BY regexreplace(file.folder, ".*\/", "") AS "Carpeta"
```

## Resúmenes Pendientes

```dataview
TASK
FROM "4to Semestre"
WHERE !completed and file.name != this.file.name and status = "<"
GROUP BY regexreplace(file.folder, ".*\/", "") AS "Carpeta"
```

## Completadas
```dataview
TASK
FROM "4to Semestre"
WHERE completed and file.name != this.file.name
GROUP BY regexreplace(file.folder, ".*\/", "") AS "Carpeta"
```
