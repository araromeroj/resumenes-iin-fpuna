### Ejercicio 1

- **Datos:** Vida útil promedio histórica de 1200 horas. Se toma una muestra de 10 bombillas con los valores: 1280, 1245, 1300, 1325, 1250, 1285, 1310, 1260, 1295, 1305. Nivel de significancia de 0.05.
    
- **Estadísticos:** Media muestral $\overline{x} = 1285.5$, desviación estándar muestral $s \approx 24.88$, $n = 10$.
    
- **Hipótesis:** $H_0: \mu \le 1200$; $H_1: \mu > 1200$ (Prueba de cola derecha).
    
- **Cálculo:**
    
    $$t = \frac{1285.5 - 1200}{24.88 / \sqrt{10}} \approx 10.86$$
    
- **Conclusión:** Con grados de libertad $df = 9$, el valor crítico de T para un nivel de significancia de 0.05 (cola derecha) es 1.833. Como 10.86 > 1.833, se rechaza $H_0$. Puede concluirse que la vida útil promedio es superior a 1200 horas.
    

### Ejercicio 2

- **Datos:** Precio medio histórico de 4.35 pesos. Muestra de diez artículos con precios: 4.41, 4.47, 4.33, 4.35, 4.30, 4.39, 4.36, 4.38, 4.40, 4.39. Nivel de significancia de 0.01.
    
- **Estadísticos:** $\overline{x} \approx 4.378$, $s \approx 0.046$, $n = 10$.
    
- **Hipótesis:** $H_0: \mu \le 4.35$; $H_1: \mu > 4.35$.
    
- **Cálculo:**
    
    $$t = \frac{4.378 - 4.35}{0.046 / \sqrt{10}} \approx 1.92$$
    
- **Conclusión:** Para $df = 9$ y un nivel de significancia de 0.01 (cola derecha), el valor crítico es 2.821. Como 1.92 < 2.821, no se rechaza $H_0$. No hay evidencia suficiente para afirmar que el accesorio aumentó el precio medio.
    

### Ejercicio 3

- **Datos:** Producción diaria de la Planta A (45, 49, 53, 51, 47, 52, 50) y Planta B (55, 48, 50, 54, 52, 56, 53, 51). Nivel de significancia del 0.05.
    
- **Estadísticos:** Planta A: $n_A = 7$, $\overline{x}_A \approx 49.57$, $s_A \approx 2.76$. Planta B: $n_B = 8$, $\overline{x}_B = 52.375$, $s_B \approx 2.62$.
    
- **Hipótesis:** $H_0: \mu_A = \mu_B$; $H_1: \mu_A \neq \mu_B$ (Prueba de dos colas).
    
- **Cálculo:** Desviación estándar combinada $s_p \approx 2.685$.
    
    $$t = \frac{49.57 - 52.375}{2.685 \sqrt{\frac{1}{7} + \frac{1}{8}}} \approx -2.02$$
    
- **Conclusión:** Para $df = 13$ y nivel de significancia de 0.05 (dos colas), el valor crítico es $\pm 2.160$. Como el estadístico t se encuentra en el rango de no rechazo (-2.02 está entre -2.160 y 2.160), no se rechaza $H_0$. No se puede concluir que la producción promedio sea diferente.
    

### Ejercicio 4

- **Datos:** Dos muestras aleatorias de 10 botellas para la Máquina 1 y Máquina 2. Volumen neto esperado de 16 onzas.
    
- **Estadísticos:** M1: $\overline{x}_1 = 16.015$, $s_1 \approx 0.030$. M2: $\overline{x}_2 = 16.005$, $s_2 \approx 0.025$.
    
- **Hipótesis:** $H_0: \mu_1 = \mu_2$; $H_1: \mu_1 \neq \mu_2$.
    
- **Cálculo:**
    
    $$t = \frac{16.015 - 16.005}{0.0276 \sqrt{0.2}} \approx 0.81$$
    
- **Conclusión:** Para $df = 18$ a un nivel de significancia típico de 0.05 (dos colas), el valor crítico es $\pm 2.101$. El valor de prueba de 0.81 cae en la región de aceptación. El ingeniero se encuentra en lo correcto al sospechar que los volúmenes son iguales.
    

### Ejercicio 5

- **Datos:** El Proveedor A tiene muestra de 10 piezas, promedio 45300 psi, desviación 250. Proveedor B tiene 12 piezas, promedio 44700 psi, desviación 300. Se desea verificar si el A supera al B por al menos 500 psi con nivel de significancia de 0.05.
    
- **Hipótesis:** $H_0: \mu_A - \mu_B \le 500$; $H_1: \mu_A - \mu_B > 500$.
    
- **Cálculo:** Diferencia de medias es 600. Desviación combinada $s_p \approx 278.6$. Error estándar $\approx 119.28$.
    
    $$t = \frac{600 - 500}{119.28} \approx 0.838$$
    
- **Conclusión:** Para $df = 20$, el valor crítico con un nivel de significancia de 0.05 (una cola) es 1.725. Como 0.838 < 1.725, no se rechaza $H_0$. La empresa no debería seleccionar al Proveedor A basándose en esta exigencia estricta.
    

### Ejercicio 6

- **Datos:** Duración media pasada de 1120 horas con desviación típica de 125 horas. Muestra actual de 8 bombillas da media de 1070 horas. Nivel de significancia de 5% ($\alpha=0.05$).
    
- **Hipótesis:** $H_0: \mu = 1120$; $H_1: \mu < 1120$.
    
- **Cálculo:** Utilizando la desviación estándar como estimador poblacional o asumiendo distribución t por el tamaño pequeño:
    
    $$t = \frac{1070 - 1120}{125 / \sqrt{8}} \approx -1.13$$
    
- **Conclusión:** Para $df = 7$, el valor crítico de nivel de significancia de 0.05 es -1.895. No se rechaza la hipótesis nula puesto que -1.13 > -1.895.
    

### Ejercicio 7

- **Datos:** Datos pareados de tiempo promedio en 12 rutas distintas, antes y después del sistema. Nivel de significancia de 0.02.
    
- **Estadísticos (Diferencias):** $\overline{d} = 6.75$ minutos de reducción en promedio. $s_d \approx 3.33$.
    
- **Hipótesis:** $H_0: \mu_d \le 0$; $H_1: \mu_d > 0$.
    
- **Cálculo:**
    
    $$t = \frac{6.75}{3.33 / \sqrt{12}} \approx 7.02$$
    
- **Conclusión:** Para $df = 11$ (datos pareados), el estadístico T es masivo (valor crítico aproximado 2.328). Se rechaza $H_0$. El nuevo sistema es altamente efectivo en la reducción del tiempo.
    

### Ejercicio 8

- **Datos:** 6 muestras de lodo arrojan media de 6.68 de PH y desviación estándar muestral de 0.20. Nivel de significancia $\alpha=0.01$.
    
- **Hipótesis:** $H_0: \mu \ge 7.0$; $H_1: \mu < 7.0$.
    
- **Cálculo:**
    
    $$t = \frac{6.68 - 7.0}{0.20 / \sqrt{6}} \approx -3.92$$
    
- **Conclusión:** Con $df = 5$, el valor crítico de nivel de significancia de 0.01 es -3.365. Como -3.92 < -3.365, se rechaza $H_0$. Se concluye que el PH medio es menor que 7.0.
    

### Ejercicio 9

- **Datos:** Máquina 1: $n_1=20$, media 750, desviación 30. Máquina 2: $n_2=25$, media 770, desviación 40. Nivel de significancia de 0.10.
    
- **Hipótesis:** $H_0: \mu_1 = \mu_2$; $H_1: \mu_1 \neq \mu_2$.
    
- **Cálculo:** Varianza combinada $s_p^2 \approx 1290.7$, $s_p \approx 35.9$. Error Estándar $\approx 10.77$.
    
    $$t = \frac{750 - 770}{10.77} \approx -1.85$$
    
- **Conclusión:** Con $df = 43$, el valor crítico de dos colas al 10% es aproximadamente $\pm 1.68$. Como -1.85 cae en la región de rechazo, existe evidencia para afirmar que tienen una vida útil significativamente diferente.
    

### Ejercicio 10

- **Datos:** Rendimiento promedio histórico de 13 puntos. Muestra aleatoria de 20 alumnos con rendimiento promedio de 14.5 puntos y desviación estándar de 1.5 puntos. Nivel de significancia del 5%.
    
- **Hipótesis:** $H_0: \mu \le 13$; $H_1: \mu > 13$.
    
- **Cálculo:**
    
    $$t = \frac{14.5 - 13}{1.5 / \sqrt{20}} \approx 4.47$$
    
- **Conclusión:** Con $df = 19$, el valor crítico de 0.05 es 1.729. Al ser 4.47 > 1.729, se rechaza $H_0$. Hay evidencia para afirmar que la percepción del Director es cierta.
    

### Ejercicio 11

- **Datos:** Peso promedio deseado de 4 libras. Muestra de 24 personas con registro de cambio de peso. Nivel de significancia de 0.01.
    
- **Estadísticos:** La sumatoria de las 24 observaciones es 100, con una media $\overline{x} \approx 4.167$ y desviación estándar $s \approx 1.76$.
    
- **Hipótesis:** $H_0: \mu = 4$; $H_1: \mu \neq 4$.
    
- **Cálculo:**
    
    $$t = \frac{4.167 - 4}{1.76 / \sqrt{24}} \approx 0.46$$
    
- **Conclusión:** Con $df = 23$, y un nivel de significancia de 0.01 (dos colas, asumiendo búsqueda de diferencia significativa general), el estadístico t de 0.46 está lejos del punto de rechazo crítico de $\pm 2.807$. El suplemento no tiene un impacto significativamente diferente a las 4 libras esperadas.
    

### Ejercicio 12

- **Datos:** Dos grupos independientes con Método A ($n=9$) y Método B ($n=7$). Nivel de significación 0.10.
    
- **Estadísticos:** Método A: $\overline{x}_A = 15$, $s_A \approx 1.414$. Método B: $\overline{x}_B = 13$, $s_B \approx 1.155$.
    
- **Hipótesis:** $H_0: \mu_A = \mu_B$; $H_1: \mu_A \neq \mu_B$.
    
- **Cálculo:** Desviación combinada $s_p \approx 1.31$.
    
    $$t = \frac{15 - 13}{1.31 \sqrt{\frac{1}{9} + \frac{1}{7}}} \approx 3.03$$
    
- **Conclusión:** Con $df = 14$, el valor crítico bidireccional para el nivel de significación 0.10 es $\pm 1.761$. Como 3.03 > 1.761, se rechaza $H_0$. Los resultados apoyan la hipótesis de investigación.
    

### Ejercicio 13

- **Datos:** Afirmación de que el 75% de las personas mayores de 65 años tienen problemas de audición. Encuesta a 200 personas y 140 presentan problemas. Nivel de significación $\alpha=0.05$.
    
- **Nota:** Al ser una proporción con muestra grande ($n=200$), se utiliza la aproximación normal (Z), que equivale a T con $df = \infty$.
    
- **Hipótesis:** $H_0: p = 0.75$; $H_1: p \neq 0.75$.
    
- **Cálculo:** Proporción de la muestra $\hat{p} = \frac{140}{200} = 0.70$.
    
    $$Z = \frac{0.70 - 0.75}{\sqrt{\frac{0.75 \times 0.25}{200}}} \approx -1.63$$
    
- **Conclusión:** El valor crítico Z (o t con $df=\infty$) a dos colas al 5% es $\pm 1.96$. Como -1.63 se encuentra dentro del intervalo de aceptación, no se puede rechazar $H_0$. Puede mantenerse la hipótesis.
    

### Ejercicio 14

- **Datos:** Ventas en miles de dólares para el País A (muestra de 9) y País B (muestra de 6). Nivel de significación de 4%.
    
- **Estadísticos:** País A: $\overline{x}_A = 58$, $s_A \approx 10.42$. País B: $\overline{x}_B \approx 51.83$, $s_B \approx 12.35$.
    
- **Hipótesis:** $H_0: \mu_A = \mu_B$; $H_1: \mu_A \neq \mu_B$.
    
- **Cálculo:** Desviación combinada $s_p \approx 11.2$.
    
    $$t = \frac{58 - 51.83}{11.2 \sqrt{\frac{1}{9} + \frac{1}{6}}} \approx 1.04$$
    
- **Conclusión:** Con $df = 13$, el valor crítico de T al 4% (dos colas) es aproximadamente $\pm 2.28$. El estadístico t de 1.04 no alcanza la zona de rechazo, por lo que no se rechaza $H_0$. No se considera que la diferencia sea estadísticamente significativa.