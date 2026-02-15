## Primer Parcial
```dataview
TABLE 
    profesor AS "Profesor", 
    parcial_1 AS "1er Parcial", 
    (parcial_1 - date(today)) AS "Días para el examen"
FROM "4TO CON BDD (prueba)/Materias"
WHERE tipo = "materia"
SORT parcial_1 ASC
```
## Segundo Parcial
```dataview
TABLE 
    profesor AS "Profesor", 
    parcial_2 AS "2do Parcial", 
    (parcial_2 - date(today)) AS "Días para el examen"
FROM "4TO CON BDD (prueba)/Materias"
WHERE tipo = "materia"
SORT parcial_2 ASC
```
## Primer Final
```dataview
TABLE 
    profesor AS "Profesor", 
    final_1 AS "1er Parcial", 
    (final_1 - date(today)) AS "Días para el examen"
FROM "4TO CON BDD (prueba)/Materias"
WHERE tipo = "materia"
SORT final_1 ASC
```
## Segundo Final
```dataview
TABLE 
    profesor AS "Profesor", 
    final_2 AS "1er Parcial", 
    (final_2 - date(today)) AS "Días para el examen"
FROM "4TO CON BDD (prueba)/Materias"
WHERE tipo = "materia"
SORT final_2 ASC
```
