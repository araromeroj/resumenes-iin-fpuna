
```dataviewjs
let rows = [];

for (let page of dv.pages('"5to Semestre/_Materias5"')) {
    let eventos = [
        { tipo: "1º Parcial", fecha: page.parcial_1 },
        { tipo: "2º Parcial", fecha: page.parcial_2 },
        { tipo: "1º Final", fecha: page.final_1 },
        { tipo: "2º Final", fecha: page.final_2 },
        { tipo: "Lab 1", fecha: page.lab1 },
        { tipo: "Lab 2", fecha: page.lab2 },
        { tipo: "Lab 3", fecha: page.lab3 },
        { tipo: "Lab 4", fecha: page.lab4 }
    ];

    for (let item of eventos) {
        if (item.fecha && dv.date(item.fecha) && !item.fecha.toString().includes("AAAA")) {
            rows.push([
                dv.date(item.fecha),
                page.file.link,
                item.tipo,
                dv.date(item.fecha).toFormat("dd/MM/yyyy - HH:mm")
            ]);
        }
    }
}

// Ordenar por fecha más cercana
rows.sort((a, b) => a[0] - b[0]);

dv.table(["Materia", "Evento", "Fecha y Hora"], rows.map(r => [r[1], r[2], r[3]]));
```
---

