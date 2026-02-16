## Primer Parcial - Abril
```dataview
TABLE 
    profesor AS "Profesor", 
    dateformat(parcial_1, "dd/MM") AS "1er Parcial", 
    (parcial_1 - date(today)) AS "Días restantes"
FROM "4to Semestre/Materias"
WHERE tipo = "materia"
SORT parcial_1 ASC
```

## Segundo Parcial - Mayo
```dataview
TABLE 
    profesor AS "Profesor", 
    dateformat(parcial_2, "dd/MM") AS "2do Parcial", 
    (parcial_2 - date(today)) AS "Días restantes"
FROM "4to Semestre/Materias"
WHERE tipo = "materia"
SORT parcial_2 ASC
```

---
## Primer Final - Junio
```dataview
TABLE 
    profesor AS "Profesor", 
    dateformat(final_1, "dd/MM") AS "1er Final", 
    (final_1 - date(today)) AS "Días restantes"
FROM "4to Semestre/Materias"
WHERE tipo = "materia"
SORT final_1 ASC
```

## Segundo Final - Julio
```dataview
TABLE 
    profesor AS "Profesor", 
    dateformat(final_2, "dd/MM") AS "2do Final", 
    (final_2 - date(today)) AS "Días restantes"
FROM "4to Semestre/Materias"
WHERE tipo = "materia"
SORT final_2 ASC
```
