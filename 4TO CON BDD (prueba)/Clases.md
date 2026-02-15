## Lunes
```dataview
TABLE 
    regexreplace(item, "^.* (\d{2}:\d{2})-\d{2}:\d{2}$", "$1") AS "Inicio",
    regexreplace(item, "^.* \d{2}:\d{2}-(\d{2}:\d{2})$", "$2") AS "Fin",
    aula AS "Aula"
FROM "4TO CON BDD (prueba)/Materias"
FLATTEN horario as item
WHERE contains(item, "Lunes")
```

## Martes
```dataview
TABLE 
    regexreplace(item, "^.* (\d{2}:\d{2})-\d{2}:\d{2}$", "$1") AS "Inicio",
    regexreplace(item, "^.* \d{2}:\d{2}-(\d{2}:\d{2})$", "$2") AS "Fin",
    aula AS "Aula"
FROM "4TO CON BDD (prueba)/Materias"
FLATTEN horario as item
WHERE contains(item, "Martes")
```

## Miércoles
```dataview
TABLE 
    regexreplace(item, "^.* (\d{2}:\d{2})-\d{2}:\d{2}$", "$1") AS "Inicio",
    regexreplace(item, "^.* \d{2}:\d{2}-(\d{2}:\d{2})$", "$2") AS "Fin",
    aula AS "Aula"
FROM "4TO CON BDD (prueba)/Materias"
FLATTEN horario as item
WHERE contains(item, "Miércoles")
```

## Jueves
```dataview
TABLE 
    regexreplace(item, "^.* (\d{2}:\d{2})-\d{2}:\d{2}$", "$1") AS "Inicio",
    regexreplace(item, "^.* \d{2}:\d{2}-(\d{2}:\d{2})$", "$2") AS "Fin",
    aula AS "Aula"
FROM "4TO CON BDD (prueba)/Materias"
FLATTEN horario as item
WHERE contains(item, "Jueves")
```

## Viernes
```dataview
TABLE 
    regexreplace(item, "^.* (\d{2}:\d{2})-\d{2}:\d{2}$", "$1") AS "Inicio",
    regexreplace(item, "^.* \d{2}:\d{2}-(\d{2}:\d{2})$", "$2") AS "Fin",
    aula AS "Aula"
FROM "4TO CON BDD (prueba)/Materias"
FLATTEN horario as item
WHERE contains(item, "Viernes")
```

