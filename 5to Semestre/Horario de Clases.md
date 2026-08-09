## Horario
### Lunes
```dataview
TABLE 
	split(replace(h, "Lunes ", ""), "-")[0] as "Inicio",
	split(replace(h, "Lunes ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia"
  AND contains(h, "Lunes")
SORT split(h, " ")[1] ASC
```

### Martes
```dataview
TABLE
	split(replace(h, "Martes ", ""), "-")[0] as "Inicio",
	split(replace(h, "Martes ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia" 
  AND contains(h, "Martes")
SORT split(h, " ")[1] ASC
```

### Miércoles
```dataview
TABLE 
	split(replace(h, "Miércoles ", ""), "-")[0] as "Inicio",
	split(replace(h, "Miércoles ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia" 
  AND contains(h, "Miércoles")
SORT split(h, " ")[1] ASC
```

### Jueves
```dataview
TABLE 
	split(replace(h, "Jueves ", ""), "-")[0] as "Inicio",
	split(replace(h, "Jueves ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia" 
  AND contains(h, "Jueves")
SORT split(h, " ")[1] ASC
```

### Viernes
```dataview
TABLE 
	split(replace(h, "Viernes ", ""), "-")[0] as "Inicio",
	split(replace(h, "Viernes ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia" 
  AND contains(h, "Viernes")
SORT split(h, " ")[1] ASC
```

### Sábado
```dataview
TABLE 
	split(replace(h, "Viernes ", ""), "-")[0] as "Inicio",
	split(replace(h, "Viernes ", ""), "-")[1] as "Fin",
	aula AS "Aula"
FROM "5to Semestre/_Materias5"
FLATTEN horario as h
WHERE tipo = "materia" 
  AND contains(h, "Sábado")
SORT split(h, " ")[1] ASC
```

## Laboratorios

```dataview
TABLE 
  dateformat(fecha_lab, "EEEE") AS "Día", 
  dateformat(fecha_lab, "dd/MM/yyyy") AS "Fecha", 
  dateformat(fecha_lab, "HH:mm") AS "Hora"
WHERE tipo = "laboratorio"
FLATTEN list(lab1, lab2, lab3, lab4) AS fecha_lab
WHERE fecha_lab != null AND fecha_lab >= date(now)
SORT fecha_lab ASC
```

## Profes y Secciones

```dataview
TABLE profesor, seccion, aula
FROM "5to Semestre/_Materias5"
WHERE tipo = "materia"
```

