## 1. Generar Tablas
````
```dataview
TABLE 
    parcial_1 AS "Fecha 1er Parcial", 
    (parcial_1 - date(today)) AS "Días Restantes"
FROM ""
WHERE tipo = "materia" AND parcial_1 >= date(today)
SORT parcial_1 ASC
````
## 2. Cómo pedir "detalles"
### A. "Muéstrame solo lo que rindo en Abril"

```sql
```dataview
LIST FROM ""
WHERE tipo = "materia" AND parcial_1.month = 4
````

### B. "Dime quiénes son mis profesores y mi sección"
Para cuando necesites completar un formulario o buscar al docente:
```sql
```dataview
TABLE profesor, seccion
FROM ""
WHERE tipo = "materia"
````

### C. "Lista de materias que rindo a la tarde (después de las 14:00)"

```sql
```dataview
TABLE parcial_1, horario
FROM ""
WHERE tipo = "materia" AND contains(horario, "14:") OR contains(horario, "15:")
````

## 3. ¿Cómo "hablarle" a Dataview? (Guía rápida)

1.  **SELECT (`TABLE` o `LIST`):** ¿Cómo quieres ver la info? ¿En tabla o en lista?
2.  **FROM:** ¿De dónde saco la info? (Si dejas `""` busca en toda tu bóveda).
3.  **WHERE:** ¿Qué condiciones deben cumplirse? (Ej: `donde el profesor sea Osvaldo Vega`).
4.  **SORT:** ¿Cómo lo ordeno? (Ej: `por fecha de forma ascendente`).