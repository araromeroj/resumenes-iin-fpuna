## Pendientes
```sql
```dataview
TASK
FROM "4to Semestre"
WHERE !completed
GROUP BY file.link
```

## Índices

### Índice de materia

Muestra las notas de una carpeta de manera ascendente de acuerdo al nombre (crea un enlace)

```sql
```dataview
LIST
FROM "Carpeta"
SORT file.name ASC
```

### Índice de Estado o Etiquetas

Muestra de qué trata cada nota o en qué estado se encuentra

```sql
```dataview
TABLE tags AS "Etiquetas", estatus AS "Estado"
FROM "Nombre de tu Carpeta"
WHERE file.name != this.file.name
SORT file.name ASC
```

## Tablas

```sql
```dataview
TABLE 
    parcial_1 AS "Fecha 1er Parcial", 
    (parcial_1 - date(today)) AS "Días Restantes"
FROM ""
WHERE tipo = "materia" AND parcial_1 >= date(today)
SORT parcial_1 ASC
```

### Clases de Hoy

```sql
```dataview
TABLE 
    split(replace(h, dateformat(date(today), "cccc"), ""), "-")[0] as "Inicio",
    aula as "Aula"
FROM "4to Semestre/Materias"
FLATTEN horario as h
WHERE contains(h, dateformat(date(today), "cccc"))
```

### Exámenes en los próximos {x} días

```sql
```dataview
TABLE 
    parcial_1 as "Fecha",
    (parcial_1 - date(today)) as "Faltan"
FROM ""
WHERE parcial_1 - date(today) <= dur(15 days) AND parcial_1 >= date(today)
SORT parcial_1 ASC
```

### Muestra un mensaje si falta menos de 7 días para una fecha

```sql
```dataview
TABLE
	choice(parcial_1 - date(today) <= dur(7 days) AND parcial_1 >= date(today), 
        "⚠️ ¡ESTUDIAR YA!", 
        choice(parcial_1 < date(today), "✅ Finalizado", "⏳ Faltan " + (parcial_1 - date(today)).days + " días")
    ) as "Estado"
```

## Calendario

```sql
```dataview
CALENDAR parcial_1
FROM ""
WHERE tipo = "materia"
```

## Detalles y Consultas

- **LIST:** Ideal para un resumen rápido de "Materias del Semestre".
    
- **TASK:** Para ver tareas pendientes de todas las notas.
    
- **CALENDAR:** Para visualizar fechas de exámenes en un calendario.

### Tareas Pendientes
Muestra todas las tareas
```sql
```dataview
TABLE 
    vencimiento as "Vence",
    choice(vencimiento < date(today), "🔴 VENCIDO", "🟢 A tiempo") as "Estado"
FROM "Facultad"
WHERE !completed AND vencimiento
SORT vencimiento ASC
```

Muestra todas las tareas pendientes por hacer
```sql
```dataview
TASK
FROM ""
WHERE !completed
GROUP BY file.link
```
### "Muéstrame solo lo que rindo en {mes}"

```sql
```dataview
LIST FROM ""
WHERE tipo = "materia" AND parcial_1.month = 4
```

### "Dime quiénes son mis profesores y mi sección"

```sql
```dataview
TABLE profesor, seccion
FROM ""
WHERE tipo = "materia"
````

### "Lista de materias que curso a la tarde (después de las 14:00)"

```sql
```dataview
TABLE parcial_1, horario
FROM ""
WHERE tipo = "materia" AND contains(horario, "14:") OR contains(horario, "15:")
````

## Guía Rápida

1.  **SELECT (`TABLE` o `LIST`):** ¿Cómo quieres ver la info? ¿En tabla o en lista?
2.  **FROM:** ¿De dónde saco la info? (Si dejas `""` busca en toda tu bóveda).
3.  **WHERE:** ¿Qué condiciones deben cumplirse? (Ej: `donde el profesor sea Osvaldo Vega`).
4.  **SORT:** ¿Cómo lo ordeno? (Ej: `por fecha de forma ascendente`).

