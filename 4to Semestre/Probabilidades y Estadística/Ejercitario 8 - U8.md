### Ejercicio 1

- **Datos:** $\mu_0 = 1.28$, $n = 40$, $\bar{x} = 1.08$, $s = 0.5$, $\alpha = 0.05$ (Unilateral izquierda).
    
- **Hipótesis:**
    
    $H_0: \mu \ge 1.28$
    
    $H_1: \mu < 1.28$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\bar{x} - \mu_0}{s / \sqrt{n}} = \frac{1.08 - 1.28}{0.5 / \sqrt{40}} = \frac{-0.20}{0.07906} \approx -2.53$$
    
- **Región de rechazo:** Para $\alpha = 0.05$, el valor crítico es $Z_{\text{crítico}} = -1.645$. Se rechaza $H_0$ si $Z_{\text{calculado}} < -1.645$.
    
- **Conclusión:** Como $-2.53 < -1.645$, se **rechaza $H_0$**. Existe evidencia estadística suficiente al 5% para afirmar que la vida útil real es menor que la especificada por el fabricante.
    

### Ejercicio 2

- **Datos:** $p_0 = 0.40$, $n = 450$, $x = 200 \Rightarrow \hat{p} = \frac{200}{450} \approx 0.4444$, $\alpha = 0.01$ (Bilateral).
    
- **Hipótesis:**
    
    $H_0: p = 0.40$
    
    $H_1: p \neq 0.40$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}} = \frac{0.4444 - 0.40}{\sqrt{\frac{0.40 \times 0.60}{450}}} = \frac{0.0444}{0.02309} \approx 1.92$$
    
- **Región de rechazo:** Para $\alpha = 0.01$ bilateral, los valores críticos son $\pm 2.575$.
    
- **Conclusión:** Como $-2.575 < 1.92 < 2.575$, **no se rechaza $H_0$**. No hay evidencia suficiente al 1% para contradecir los estudios anteriores; la proporción se mantiene en el 40%.
    

### Ejercicio 3

- **Datos:**
    
    - Grupo 1: $n_1 = 36$, $\bar{x}_1 = 6$, $s_1 = 4$
        
    - Grupo 2: $n_2 = 40$, $\bar{x}_2 = 8.2$, $s_2 = 4.3$
        
    - $\alpha = 0.02$ (Unilateral derecha para $H_1: \mu_2 > \mu_1$).
        
- **Hipótesis:**
    
    $H_0: \mu_2 - \mu_1 \le 0$
    
    $H_1: \mu_2 - \mu_1 > 0$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\bar{x}_2 - \bar{x}_1}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}} = \frac{8.2 - 6}{\sqrt{\frac{4^2}{36} + \frac{4.3^2}{40}}} = \frac{2.2}{\sqrt{0.4444 + 0.4623}} = \frac{2.2}{0.9522} \approx 2.31$$
    
- **Región de rechazo:** Para $\alpha = 0.02$ unilateral derecha, $Z_{\text{crítico}} = 2.05$.
    
- **Conclusión:** Como $2.31 > 2.05$, se **rechaza $H_0$**. Se concluye que el método aplicado al segundo grupo fue estadísticamente superior al del primero con un nivel de significancia del 2%.
    

### Ejercicio 4

- **Datos:**
    
    - Sucursal 1: $n_1 = 120$, $x_1 = 12 \Rightarrow \hat{p}_1 = 0.10$
        
    - Sucursal 2: $n_2 = 120$, $x_2 = 16 \Rightarrow \hat{p}_2 = 0.1333$
        
    - $\alpha = 0.05$ (Bilateral).
        
- **Proporción combinada ($\bar{p}$):** $\bar{p} = \frac{12 + 16}{120 + 120} = \frac{28}{240} \approx 0.1167$
    
- **Hipótesis:**
    
    $H_0: p_1 = p_2$
    
    $H_1: p_1 \neq p_2$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\hat{p}_1 - \hat{p}_2}{\sqrt{\bar{p}(1-\bar{p})\left(\frac{1}{n_1} + \frac{1}{n_2}\right)}} = \frac{0.10 - 0.1333}{\sqrt{0.1167 \times 0.8833 \times \left(\frac{1}{120} + \frac{1}{120}\right)}} = \frac{-0.0333}{0.0414} \approx -0.80$$
    
- **Región de rechazo:** Para $\alpha = 0.05$ bilateral, los valores críticos son $\pm 1.96$.
    
- **Conclusión:** Como $-1.96 < -0.80 < 1.96$, **no se rechaza $H_0$**. Al nivel del 5%, se puede afirmar que el porcentaje de accidentes laborales es estadísticamente igual en ambas sucursales.
    

### Ejercicio 5

- **Datos:** $\mu_0 = 500$, $n = 49$, $\bar{x} = 502.8$, $\sigma = 6$, $\alpha = 0.01$ (Unilateral derecha, sospecha de llenado "por encima").
    
- **Hipótesis:**
    
    $H_0: \mu \le 500$
    
    $H_1: \mu > 500$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}} = \frac{502.8 - 500}{6 / \sqrt{49}} = \frac{2.8}{6 / 7} = \frac{2.8}{0.8571} \approx 3.27$$
    
- **Región de rechazo:** Para $\alpha = 0.01$ unilateral derecha, $Z_{\text{crítico}} = 2.33$.
    
- **Conclusión:** Como $3.27 > 2.33$, se **rechaza $H_0$**. La sospecha del supervisor es correcta con un nivel de significancia del 1%; se está llenando por encima de la media.
    

### Ejercicio 6

- **Datos:** $\mu_0 = 220$, $n = 50$, $\bar{x} = 221.12$, $\sigma = 2.5$, $\alpha = 0.03$ (Bilateral, "hacia arriba o hacia abajo").
    
- **Hipótesis:**
    
    $H_0: \mu = 220$
    
    $H_1: \mu \neq 220$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}} = \frac{221.12 - 220}{2.5 / \sqrt{50}} = \frac{1.12}{0.3536} \approx 3.17$$
    
- **Región de rechazo:** Para $\alpha = 0.03$ bilateral, la confianza es $0.97$. $Z_{\text{crítico}} = \pm 2.17$.
    
- **Conclusión:** Como $3.17 > 2.17$, se **rechaza $H_0$**. Existe fuerte evidencia estadística al 3% de que el proceso de fabricación se ha desviado de su valor nominal.
    

### Ejercicio 7

- **Datos:** $n = 800$, $x = 40 \Rightarrow \hat{p} = \frac{40}{800} = 0.05$, $\alpha = 0.05$.
    
- **a) Hipótesis:** $H_0: p \le 0.05$ vs $H_1: p > 0.05$ (Unilateral derecha).
    
    $$Z = \frac{0.05 - 0.05}{\sqrt{\frac{0.05 \times 0.95}{800}}} = 0$$
    
    - _Crítico:_ $Z = 1.645$. Como $0 < 1.645$, **no se rechaza $H_0$**. El estudio **no apoya** que más del 5% no conozca el programa.
        
- **b) Hipótesis:** $H_0: p \ge 0.03$ vs $H_1: p < 0.03$ (Unilateral izquierda).
    
    $$Z = \frac{0.05 - 0.03}{\sqrt{\frac{0.03 \times 0.97}{800}}} = \frac{0.02}{0.00603} \approx 3.32$$
    
    - _Crítico:_ $Z = -1.645$. Como $3.32 > -1.645$, **no se rechaza $H_0$**. El estudio **no apoya** que menos del 3% no conozca el programa.
        

### Ejercicio 8

- **Datos:** $n = 500$, $x = 15 \Rightarrow \hat{p} = \frac{15}{500} = 0.03$, $\alpha = 0.01$.
    
- **c) Hipótesis:** $H_0: p \le 0.05$ vs $H_1: p > 0.05$.
    
    $$Z = \frac{0.03 - 0.05}{\sqrt{\frac{0.05 \times 0.95}{500}}} = \frac{-0.02}{0.00975} \approx -2.05$$
    
    - _Crítico:_ $Z = 2.33$. No está en región de rechazo. **No apoya la hipótesis c)**.
        
- **d) Hipótesis:** $H_0: p \ge 0.02$ vs $H_1: p < 0.02$.
    
    $$Z = \frac{0.03 - 0.02}{\sqrt{\frac{0.02 \times 0.98}{500}}} = \frac{0.01}{0.00626} \approx 1.60$$
    
    - _Crítico:_ $Z = -2.33$. No está en región de rechazo. **No apoya la hipótesis d)**.
        

### Ejercicio 9

- **Datos:** $p_0 = 0.80$, $n = 600$, $x = 450 \Rightarrow \hat{p} = \frac{450}{600} = 0.75$, $\alpha = 0.01$ (Bilateral).
    
- **Hipótesis:**
    
    $H_0: p = 0.80$
    
    $H_1: p \neq 0.80$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{0.75 - 0.80}{\sqrt{\frac{0.80 \times 0.20}{600}}} = \frac{-0.05}{0.01633} \approx -3.06$$
    
- **Región de rechazo:** Para $\alpha = 0.01$ bilateral, valores críticos $\pm 2.575$.
    
- **Conclusión:** Como $-3.06 < -2.575$, se **rechaza $H_0$**. La afirmación de la empresa de investigación es estadísticamente falsa al nivel del 1%.
    

### Ejercicio 10

- **Datos:** $p_0 = 0.50$, $n = 300$, $x = 120 \Rightarrow \hat{p} = \frac{120}{300} = 0.40$, $\alpha = 0.10$ (Bilateral).
    
- **Hipótesis:**
    
    $H_0: p = 0.50$
    
    $H_1: p \neq 0.50$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{0.40 - 0.50}{\sqrt{\frac{0.50 \times 0.50}{300}}} = \frac{-0.10}{0.02887} \approx -3.46$$
    
- **Región de rechazo:** Para $\alpha = 0.10$ bilateral, valores críticos $\pm 1.645$.
    
- **Conclusión:** Como $-3.46 < -1.645$, se **rechaza $H_0$**. La afirmación del informe no es correcta al nivel de significación del 10%.
    

### Ejercicio 11

- **Datos:** $p_0 = 0.90$, $n = 250$, $x = 220 \Rightarrow \hat{p} = \frac{220}{250} = 0.88$, $\alpha = 0.01$ (Bilateral / Unilateral según enfoque de optimización, usemos bilateral para verificar la afirmación de calidad del fabricante).
    
- **Hipótesis:**
    
    $H_0: p = 0.90$
    
    $H_1: p \neq 0.90$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{0.88 - 0.90}{\sqrt{\frac{0.90 \times 0.10}{250}}} = \frac{-0.02}{0.01897} \approx -1.05$$
    
- **Región de rechazo:** Para $\alpha = 0.01$ bilateral, críticos $\pm 2.575$.
    
- **Conclusión:** Como $-2.575 < -1.05 < 2.575$, **no se rechaza $H_0$**. El cambio estadístico no es lo suficientemente significativo como para descartar el proceso o afirmar que bajó la calidad drásticamente; la empresa puede seguir usándolo ya que opera dentro de un margen tolerable bajo este nivel riguroso.
    

### Ejercicio 12

- **Datos:**
    
    - Ingenieria A ($1$): $n_1 = 35$, $\bar{x}_1 = 75$, $s_1 = 8$
        
    - Ingenieria B ($2$): $n_2 = 40$, $\bar{x}_2 = 80$, $s_2 = 6$
        
    - Confianza $85\% \Rightarrow \alpha = 0.15$ (Bilateral). Valor crítico $Z = \pm 1.44$.
        
- **Hipótesis:**
    
    $H_0: \mu_2 - \mu_1 = 6$
    
    $H_1: \mu_2 - \mu_1 \neq 6$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{(\bar{x}_2 - \bar{x}_1) - D_0}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}} = \frac{(80 - 75) - 6}{\sqrt{\frac{8^2}{35} + \frac{6^2}{40}}} = \frac{5 - 6}{\sqrt{1.8286 + 0.9}} = \frac{-1}{1.6518} \approx -0.61$$
    
- **Conclusión:** Como $-1.44 < -0.61 < 1.44$, **no se rechaza $H_0$**. Al 85% de confianza, no podemos descartar que la diferencia de promedios sea efectivamente de 6 puntos.
    

### Ejercicio 13

- **Datos:**
    
    - G1: $n_1 = 22$, $x_1 = 16 \Rightarrow \hat{p}_1 \approx 0.7273$
        
    - G2: $n_2 = 18$, $x_2 = 10 \Rightarrow \hat{p}_2 \approx 0.5556$
        
    - $\alpha = 0.05$ (Bilateral).
        
    - _(Nota: Aunque las muestras son pequeñas, el ejercitario pide aplicar aproximación por grandes muestras)_.
        
- **Proporción combinada:** $\bar{p} = \frac{16+10}{22+18} = \frac{26}{40} = 0.65$
    
- **Hipótesis:** $H_0: p_1 = p_2$ vs $H_1: p_1 \neq p_2$.
    
- **Estadístico de prueba:**
    
    $$Z = \frac{0.7273 - 0.5556}{\sqrt{0.65 \times 0.35 \times \left(\frac{1}{22} + \frac{1}{18}\right)}} = \frac{0.1717}{0.1517} \approx 1.13$$
    
- **Conclusión:** Como $-1.96 < 1.13 < 1.96$, **no se rechaza $H_0$**. Es posible concluir que la proporción es la misma en ambos grupos.
    

### Ejercicio 14

- **Datos:**
    
    - Adolescentes ($1$): $n_1 = 200$, $x_1 = 130 \Rightarrow \hat{p}_1 = 0.65$
        
    - Adultos ($2$): $n_2 = 150$, $x_2 = 90 \Rightarrow \hat{p}_2 = 0.60$
        
    - $\alpha = 0.05$ (Bilateral).
        
- **Proporción combinada:** $\bar{p} = \frac{130+90}{200+150} = \frac{220}{350} \approx 0.6286$
    
- **Hipótesis:** $H_0: p_1 = p_2$ vs $H_1: p_1 \neq p_2$.
    
- **Estadístico:**
    
    $$Z = \frac{0.65 - 0.60}{\sqrt{0.6286 \times 0.3714 \left(\frac{1}{200} + \frac{1}{150}\right)}} = \frac{0.05}{0.0522} \approx 0.96$$
    
- **Conclusión:** Como $-1.96 < 0.96 < 1.96$, **no se rechaza $H_0$**. No se puede concluir que haya diferencias significativas entre ambos rangos de edad.
    

### Ejercicio 15

- **Datos:** $\mu_0 = 500$, $\sigma = 15$, $n = 40$, $\bar{x} = 495$, Confianza = $90\% \Rightarrow \alpha = 0.10$ (Bilateral, el desvío puede ser por falta o exceso).
    
- **Hipótesis:** $H_0: \mu = 500$ vs $H_1: \mu \neq 500$.
    
- **Estadístico:**
    
    $$Z = \frac{495 - 500}{15 / \sqrt{40}} = \frac{-5}{2.3717} \approx -2.11$$
    
- **Región de rechazo:** Para $\alpha = 0.10$ bilateral, $Z_{\text{crítico}} = \pm 1.645$.
    
- **Conclusión:** Como $-2.11 < -1.645$, **se rechaza $H_0$**. La empresa **debe detener el proceso** y realizar ajustes.
    

### Ejercicio 16

- **Datos:** $\mu_0 = 250$, $\sigma = 5$, $n = 50$, $\bar{x} = 248$, Confianza = $95\% \Rightarrow \alpha = 0.05$ (Bilateral).
    
- **Hipótesis:** $H_0: \mu = 250$ vs $H_1: \mu \neq 250$.
    
- **Estadístico:**
    
    $$Z = \frac{248 - 250}{5 / \sqrt{50}} = \frac{-2}{0.7071} \approx -2.83$$
    
- **Región de rechazo:** Críticos $\pm 1.96$.
    
- **Conclusión:** Como $-2.83 < -1.96$, **se rechaza $H_0$**. La fábrica **debe detener el proceso** y ajustarlo.
    

### Ejercicio 17

- **Datos:** $p_0 = 0.65$, $n = 150$, $x = 85 \Rightarrow \hat{p} = \frac{85}{150} \approx 0.5667$, $\alpha = 0.05$ (Unilateral derecha, contratar si es $\ge 0.65$).
    
- **Hipótesis:** $H_0: p \ge 0.65$ vs $H_1: p < 0.65$.
    
- **Estadístico:**
    
    $$Z = \frac{0.5667 - 0.65}{\sqrt{\frac{0.65 \times 0.35}{150}}} = \frac{-0.0833}{0.03894} \approx -2.14$$
    
- **Conclusión:** Al ser un test orientado a la rentabilidad para contratar ($\ge 0.65$), el valor observado está muy por debajo de la meta. **No se rechaza la hipótesis de que no es rentable (o se rechaza la condición de ganancia)**. La empresa **no debe contratar** más trabajadores.
    

### Ejercicio 18

- **Datos:**
    
    - Sistema 1: $n_1 = 30$, $\bar{x}_1 = 85$, $s_1 = 5$
        
    - Sistema 2: $n_2 = 28$, $\bar{x}_2 = 90$, $s_2 = 4$
        
    - Confianza $90\% \Rightarrow \alpha = 0.10$ (Unilateral derecha, superior por más de 2).
        
- **Hipótesis:**
    
    $H_0: \mu_2 - \mu_1 \le 2$
    
    $H_1: \mu_2 - \mu_1 > 2$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{(\bar{x}_2 - \bar{x}_1) - 2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}} = \frac{(90 - 85) - 2}{\sqrt{\frac{5^2}{30} + \frac{4^2}{28}}} = \frac{3}{\sqrt{0.8333 + 0.5714}} = \frac{3}{1.1852} \approx 2.53$$
    
- **Región de rechazo:** Para $\alpha = 0.10$ unilateral derecha, $Z_{\text{crítico}} = 1.28$.
    
- **Conclusión:** Como $2.53 > 1.28$, se **rechaza $H_0$**. El segundo sistema es significativamente superior al primero por más de 2 productos/hora.
    

### Ejercicio 19

- **Datos:**
    
    - Algoritmo X ($1$): $\sigma_1^2 = 49$, $n_1 = 40$, $\bar{x}_1 = 85$
        
    - Algoritmo Y ($2$): $\sigma_2^2 = 64$, $n_2 = 60$, $\bar{x}_2 = 78$
        
    - $\alpha = 0.07$ (Unilateral izquierda, "Y es más eficiente" significa que toma _menos_ tiempo: $\mu_2 < \mu_1 \Rightarrow \mu_2 - \mu_1 < 0$).
        
- **Hipótesis:**
    
    $H_0: \mu_2 - \mu_1 \ge 0$
    
    $H_1: \mu_2 - \mu_1 < 0$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{\bar{x}_2 - \bar{x}_1}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}} = \frac{78 - 85}{\sqrt{\frac{49}{40} + \frac{64}{60}}} = \frac{-7}{\sqrt{1.225 + 1.0667}} = \frac{-7}{1.5138} \approx -4.62$$
    
- **Región de rechazo:** Para $\alpha = 0.07$, $Z_{\text{crítico}} = -1.475$.
    
- **Conclusión:** Como $-4.62 < -1.475$, se **rechaza $H_0$**. El Algoritmo Y es significativamente más eficiente que el Algoritmo X.
    

### Ejercicio 20

- **Datos:**
    
    - Campaña A ($1$): $n_1 = 45$, $\bar{x}_1 = 12.4$, $s_1 = 2.8$
        
    - Campaña B ($2$): $n_2 = 50$, $\bar{x}_2 = 11.9$, $s_2 = 3.1$
        
    - $\alpha = 0.03$ (Bilateral, "¿difieren de forma significativa?").
        
- **Hipótesis:**
    
    $H_0: \mu_1 = \mu_2$
    
    $H_1: \mu_1 \neq \mu_2$
    
- **Estadístico de prueba:**
    
    $$Z = \frac{12.4 - 11.9}{\sqrt{\frac{2.8^2}{45} + \frac{3.1^2}{50}}} = \frac{0.5}{\sqrt{0.1742 + 0.1922}} = \frac{0.5}{0.6053} \approx 0.83$$
    
- **Región de rechazo:** Para $\alpha = 0.03$ bilateral, los valores críticos son $\pm 2.17$.
    
- **Conclusión:** Como $-2.17 < 0.83 < 2.17$, **no se rechaza $H_0$**. Las diferencias observadas pueden deberse perfectamente al azar; no hay evidencia estadística para afirmar que el comportamiento frente a las campañas difiera de manera significativa.