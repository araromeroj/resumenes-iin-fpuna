
```dataview
TABLE 
    profesor AS "Profesor", 
    parcial_1 AS "1er Parcial", 
    (parcial_1 - date(today)) AS "Días para el examen"
FROM "4TO CON BDD (prueba)/Materias"
WHERE tipo = "materia"
SORT parcial_1 ASC
```
