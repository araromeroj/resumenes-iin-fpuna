Aquí tienes la resolución completa y detallada de cada uno de los 20 ejercicios del ejercitario sobre **Estimación**.

Para los cálculos de los intervalos de confianza y tamaños muestrales, utilizaremos las aproximaciones estándar de la distribución normal ($Z$) cuando los tamaños de muestra son grandes ($n \geq 30$) o cuando la desviación estándar poblacional ($\sigma$) es conocida, cumpliendo con los supuestos de las distribuciones normales indicadas en el texto.

## Ejercicio 1

**Datos:** $n = 40$, $\bar{x} = 220\text{ \ ohmic}$, $\sigma = 12\text{ \ ohmic}$.

- **a) Estime puntualmente la media poblacional.** La estimación puntual de la media poblacional ($\mu$) es la media muestral ($\bar{x}$).
    $${\mu} = \bar{x}= 220\text{ }\ohm$$
    
- **b) Interprete el valor obtenido.** Significa que, basándonos en la muestra de 40 microchips, el valor más probable para la resistencia promedio de todos los microchips de la población es de 220 ohmios.
    

## Ejercicio 2

**Datos:** $\sigma = 0,8\text{ s}$, $n = 25$, $\bar{x} = 3,2\text{ s}$.

- **a) Realice una estimación puntual de la media del tiempo de respuesta.**
    
    $$\hat{\mu} = \bar{x} = 3,2\text{ s}$$
    
- **b) ¿Qué representa este valor en términos operativos?** Representa el valor central o esperado del tiempo de respuesta del servidor para el conjunto global de peticiones bajo condiciones similares. Sirve como métrica de referencia operativa para evaluar el rendimiento del sistema.
    

## Ejercicio 3

**Datos:** $\sigma = 0,5\text{ mm}$, $n = 30$, $\bar{x} = 20,1\text{ mm}$.

- **a) Estime la media poblacional.**
    
    $$\hat{\mu} = \bar{x} = 20,1\text{ mm}$$
    
- **b) Comente si la media estimada es razonable si la especificación técnica indica 20 mm.** Sí, es bastante razonable. La media estimada ($20,1\text{ mm}$) se desvía apenas $0,1\text{ mm}$ respecto a la especificación técnica ($20\text{ mm}$). Esta pequeña diferencia entra perfectamente dentro del rango de variabilidad esperable en un proceso productivo real.
    

## Ejercicio 4

**Datos:** $n = 400$, $x = 96$ respuestas.

- **a) Estime puntualmente la proporción de respuesta poblacional.**
    
    $$\hat{p} = \frac{x}{n} = \frac{96}{400} = 0,24 \text{ (o } 24\%\text{)}$$
    
- **b) Interprete el resultado.** Se estima que el $24\%$ del total de clientes de la población objetivo responderá a la campaña de marketing por correo electrónico.
    

## Ejercicio 5

**Datos:** $\sigma = 0,05\text{ kg}$, $n = 36$, $\bar{x} = 2,02\text{ kg}$, Nivel de Confianza ($\text{NC}$) = $98\%$.

- **a) Construya un intervalo de confianza del 98% para la media.** Para un $\text{NC} = 98\%$, el valor crítico de la distribución normal es $Z_{\alpha/2} = 2,33$.
    
    $$E = Z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} = 2,33 \cdot \frac{0,05}{\sqrt{36}} = 2,33 \cdot 0,00833 = 0,0194\text{ kg}$$
    
    $$\text{IC} = \bar{x} \pm E = 2,02 \pm 0,0194 \implies [2,0006\text{ kg}; 2,0394\text{ kg}]$$
    
- **b) Interprete el intervalo.** Se tiene un $98\%$ de confianza de que el verdadero peso promedio poblacional de los envases de detergente se encuentra entre $2,0006\text{ kg}$ y $2,0394\text{ kg}$.
    

## Ejercicio 6

**Datos:** $n = 10$, $\bar{x} = 5,1\text{ s}$, $\sigma = 0,4\text{ s}$.

- **a) Calcule un intervalo de confianza del 96% para la media.** Para un $\text{NC} = 96\%$, $Z_{\alpha/2} = 2,05$.
    
    $$E = 2,05 \cdot \frac{0,4}{\sqrt{10}} = 2,05 \cdot 0,1265 = 0,2593\text{ s}$$
    
    $$\text{IC} = 5,1 \pm 0,2593 \implies [4,8407\text{ s}; 5,3593\text{ s}]$$
    
- **b) ¿Si un usuario sostiene que el tiempo promedio es de 8 seg, que se puede decir sobre esto, acorde al intervalo hallado?** La afirmación del usuario es **altamente improbable y estadísticamente rechazada**, debido a que el valor de $8\text{ s}$ está muy alejado y fuera del intervalo de confianza calculado ($[4,84; 5,36]\text{ s}$).
    

## Ejercicio 7

**Datos:** $n = 40$, $\bar{x} = 11,5\text{ h}$, $s = 2,1\text{ h}$, $\text{NC} = 92\%$.

- **a) Calcule el intervalo de confianza del 92% para la media.** Como $n \geq 30$, aproximamos por la normal. Para $\text{NC} = 92\%$, $Z_{\alpha/2} = 1,75$.
    
    $$E = 1,75 \cdot \frac{2,1}{\sqrt{40}} = 1,75 \cdot 0,3320 = 0,581\text{ h}$$
    
    $$\text{IC} = 11,5 \pm 0,581 \implies [10,919\text{ h}; 12,081\text{ h}]$$
    
- **b) Interprete el resultado en el contexto del estudio.** Existe un $92\%$ de confianza de que el tiempo promedio real de uso semanal de la app por parte de los usuarios está entre $10,92$ y $12,08$ horas.
    
- c) Halle el error absoluto cometido en la estimación del tiempo medio. Interprete su significado. El error absoluto (o margen de error) es:
    
    $$E = 0,581\text{ horas (aprox. } 35\text{ minutos y } 52\text{ segundos)}$$
    
    **Significado:** Representa la distancia máxima que se espera que exista entre la media muestral calculada ($\bar{x} = 11,5$) y la verdadera media de la población ($\mu$) con un nivel de confianza del $92\%$.
    

## Ejercicio 8

**Datos:** $\sigma^2 = 4 \implies \sigma = 2\text{ min}$, $n = 25$, $\bar{x} = 60\text{ min}$, $\text{NC} = 95\%$.

- **a) Estime el intervalo de confianza del 95% para la media.** Para un $\text{NC} = 95\%$, $Z_{\alpha/2} = 1,96$.
    
    $$E = 1,96 \cdot \frac{2}{\sqrt{25}} = 1,96 \cdot 0,4 = 0,784\text{ min}$$
    
    $$\text{IC} = 60 \pm 0,784 \implies [59,216\text{ min}; 60,784\text{ min}]$$
    
- **b) ¿Qué implica este intervalo para el fabricante?** Le asegura al fabricante, con una certeza del $95\%$, que el tiempo medio de vuelo real de ese modelo de dron se mantiene de forma muy precisa en torno a la hora de duración (con un margen de variación menor a un minuto).
    

## Ejercicio 9

**Datos:** * Máquina A: $n_A = 36$, $\bar{x}_A = 5,02\text{ mm}$, $s_A = 0,04\text{ mm}$.

- Máquina B: $n_B = 45$, $\bar{x}_B = 5,05\text{ mm}$, $s_B = 0,05\text{ mm}$.
    
- $\text{NC} = 93\% \implies Z_{\alpha/2} = 1,81$.
    
- **a) Construya un intervalo de confianza del 93% para la diferencia de medias ($\mu_A - \mu_B$).**
    
    $$E = Z_{\alpha/2} \cdot \sqrt{\frac{s_A^2}{n_A} + \frac{s_B^2}{n_B}} = 1,81 \cdot \sqrt{\frac{0,04^2}{36} + \frac{0,05^2}{45}}$$
    
    $$E = 1,81 \cdot \sqrt{0,0000444 + 0,0000555} = 1,81 \cdot 0,01 = 0,0181\text{ mm}$$
    
    $$\text{Diferencia puntual} = \bar{x}_A - \bar{x}_B = 5,02 - 5,05 = -0,03\text{ mm}$$
    
    $$\text{IC} = -0,03 \pm 0,0181 \implies [-0,0481\text{ mm}; -0,0119\text{ mm}]$$
    
- b) ¿Se puede decir que los grosores promedios son iguales? ¿Por qué? **No**, no se puede decir que sean iguales. Como el intervalo de confianza **no contiene al valor cero** (ambos límites son negativos), hay evidencia estadística de que el grosor promedio de los tornillos de la máquina B es significativamente mayor que el de la máquina A.
    
- **c) Calcule el margen de error asociado al intervalo y comente cómo afecta su magnitud a la precisión.** El margen de error es $E = 0,0181\text{ mm}$. Cuanto menor sea la magnitud de este error, más estrecho será el intervalo de confianza, lo cual se traduce en una **mayor precisión** en la estimación de la diferencia real.
    

## Ejercicio 10

**Datos:**

- Navegador A: $n_A = 42$, $\bar{x}_A = 2,3\text{ s}$, $s_A = 0,4\text{ s}$.
    
- Navegador B: $n_B = 50$, $\bar{x}_B = 2,5\text{ s}$, $s_B = 0,3\text{ s}$.
    
- $\text{NC} = 94\% \implies Z_{\alpha/2} = 1,88$.
    
- **a) Construya un intervalo de confianza del 94% para la diferencia de medias ($\mu_A - \mu_B$).**
    
    $$E = 1,88 \cdot \sqrt{\frac{0,4^2}{42} + \frac{0,3^2}{50}} = 1,88 \cdot \sqrt{0,00381 + 0,0018} = 1,88 \cdot 0,0749 = 0,1408\text{ s}$$
    
    $$\text{Diferencia puntual} = 2,3 - 2,5 = -0,2\text{ s}$$
    
    $$\text{IC} = -0,2 \pm 0,1408 \implies [-0,3408\text{ s}; -0,0592\text{ s}]$$
    
- **b) Interprete el intervalo: ¿existen evidencias de que uno de los navegadores sea más rápido?** Sí. Dado que todo el intervalo arroja valores negativos, se demuestra con un $94\%$ de confianza que el tiempo de carga del Navegador A es menor que el del Navegador B. Por lo tanto, **el Navegador A es significativamente más rápido**.
    
- **c) Si la empresa considera relevante una diferencia mínima de 0,2 s, ¿el intervalo sugiere una diferencia relevante?** Sí. La diferencia estimada estimada es precisamente de $-0,2\text{ s}$ y este valor clave se encuentra dentro de las estimaciones más probables contempladas por el intervalo construido.
    

## Ejercicio 11

**Datos:**

- Motor X: $n_X = 50$, $\bar{x}_X = 15,8$, $s_X = 0,6$.
    
- Motor Y: $n_Y = 55$, $\bar{x}_Y = 16$, $s_Y^2 = 0,64 \implies s_Y = 0,8$.
    
- $\text{NC} = 90\% \implies Z_{\alpha/2} = 1,645$.
    
- **a) Calcule un intervalo de confianza del 90% para la verdadera diferencia de medias ($\mu_X - \mu_Y$).**
    
    $$E = 1,645 \cdot \sqrt{\frac{0,6^2}{50} + \frac{0,64}{55}} = 1,645 \cdot \sqrt{0,0072 + 0,01164} = 1,645 \cdot 0,1373 = 0,2258\text{ kWh}$$
    
    $$\text{Diferencia puntual} = 15,8 - 16 = -0,2\text{ kWh}$$
    
    $$\text{IC} = -0,2 \pm 0,2258 \implies [-0,4258\text{ kWh}; +0,0258\text{ kWh}]$$
    
- **b) Interprete el resultado: ¿qué indica sobre la diferencia de consumo entre ambos modelos?** Dado que el intervalo **contiene al cero**, no existe suficiente evidencia estadística para afirmar con un $90\%$ de confianza que haya una diferencia real en el consumo energético promedio general entre ambos tipos de motores.
    
- **c) Si se buscara garantizar que el nuevo modelo consuma al menos 0,5 kWh menos, ¿qué sugiere el intervalo?** El intervalo sugiere que **no se puede garantizar** esa meta. La reducción máxima esperada a favor de X alcanza apenas los $0,4258\text{ kWh}$ (límite inferior), quedando por debajo de los $0,5\text{ kWh}$ solicitados.
    

## Ejercicio 12

**Datos:**

- Método A: $n_A = 45$, $\bar{x}_A = 36,1$, $s_A = 0,5$.
    
- Método B: $n_B = 42$, $\bar{x}_B = 35,8$, $s_B = 0,6$.
    
- $\text{NC} = 98\% \implies Z_{\alpha/2} = 2,33$.
    
- **a) Determine un intervalo de confianza del 98% para la diferencia de medias ($\mu_A - \mu_B$).**
    
    $$E = 2,33 \cdot \sqrt{\frac{0,5^2}{45} + \frac{0,6^2}{42}} = 2,33 \cdot \sqrt{0,00556 + 0,00857} = 2,33 \cdot 0,1189 = 0,277\text{ }^\circ\text{C}$$
    
    $$\text{Diferencia puntual} = 36,1 - 35,8 = 0,3\text{ }^\circ\text{C}$$
    
    $$\text{IC} = 0,3 \pm 0,277 \implies [0,023\text{ }^\circ\text{C}; 0,577\text{ }^\circ\text{C}]$$
    
- **b) Interprete el resultado: ¿parecen diferir los métodos?** Sí, parecen diferir. Al ser ambos extremos del intervalo positivos (no incluye el cero), se concluye que el Método A genera lecturas promedio ligeramente mayores que el Método B.
    
- c) Si se desea un nivel de precisión de $\pm0,2\text{ }^\circ\text{C}$, ¿qué tamaño muestral sería necesario para cada método? (Asumiendo tamaños de muestra iguales $n_A = n_B = n$ y manteniendo confianza del 98%).
    
    $$E = Z_{\alpha/2} \cdot \sqrt{\frac{s_A^2 + s_B^2}{n}} \implies n = \frac{Z_{\alpha/2}^2 \cdot (s_A^2 + s_B^2)}{E^2}$$
    
    $$n = \frac{2,33^2 \cdot (0,5^2 + 0,6^2)}{0,2^2} = \frac{5,4289 \cdot 0,61}{0,04} = \frac{3,3116}{0,04} = 82,79$$
    
    Se requeriría un tamaño muestral de **83 mediciones para cada método**.
    
- **d) Desde un punto de vista práctico, ¿qué factor pesa más: la magnitud de la diferencia o la variabilidad de las mediciones?** La **variabilidad de las mediciones** (las desviaciones estándar) suele pesar más, dado que si el proceso es muy inestable o impreciso (alta variabilidad), el margen de error crecerá tanto que camuflará e impedirá detectar si existe o no una diferencia real entre los métodos.
    

## Ejercicio 13

**Datos:** $n = 600$, $x = 420 \implies \hat{p} = \frac{420}{600} = 0,7$ y $\hat{q} = 0,3$. $\text{NC} = 97\% \implies Z_{\alpha/2} = 2,17$.

- **a) Construya un intervalo de confianza del 97% para la proporción de recicladores.**
    
    $$E = 2,17 \cdot \sqrt{\frac{0,7 \cdot 0,3}{600}} = 2,17 \cdot \sqrt{0,00035} = 2,17 \cdot 0,0187 = 0,0406 \text{ (o } 4,06\%\text{)}$$
    
    $$\text{IC} = 0,7 \pm 0,0406 \implies [0,6594; 0,7406] \implies [65,94\%; 74,06\%]$$
    
- **b) Interprete el intervalo en términos poblacionales.** Se estima con un $97\%$ de confianza que la proporción real de personas con el hábito de reciclar a nivel nacional se sitúa entre el $65,94\%$ y el $74,06\%$.
    
- **c) Si se repitiera el estudio con el doble de encuestados y la misma proporción, ¿qué ocurriría con el ancho del intervalo?** El ancho del intervalo **se reduciría** en un factor de $\sqrt{2}$ (es decir, se volvería aproximadamente un $29,3\%$ más estrecho), logrando que la estimación sea más precisa.
    
- **d) ¿Cómo se relaciona el tamaño de la muestra con la confianza en la estimación?** A un mismo nivel de confianza, un mayor tamaño muestral reduce el margen de error (intervalo más estrecho). Si quisiéramos aumentar la confianza manteniendo fijo el tamaño muestral, el intervalo necesariamente tendría que ensancharse.
    

## Ejercicio 14

**Datos:**

- Campaña A: $n_A = 200$, $x_A = 50 \implies \hat{p}_A = \frac{50}{200} = 0,25$.
    
- Campaña B: $n_B = 300$, $x_B = 90 \implies \hat{p}_B = \frac{90}{300} = 0,30$.
    
- $\text{NC} = 99\% \implies Z_{\alpha/2} = 2,576$.
    
- **a) Estime la proporción de respuesta para cada campaña.**
    
    $$\hat{p}_A = 25\% \quad \text{y} \quad \hat{p}_B = 30\%$$
    
- **b) Construya un intervalo de confianza del 99% para la diferencia real de proporciones ($p_A - p_B$).**
    
    $$E = 2,576 \cdot \sqrt{\frac{0,25 \cdot 0,75}{200} + \frac{0,30 \cdot 0,70}{300}} = 2,576 \cdot \sqrt{0,0009375 + 0,0007} = 2,576 \cdot 0,04046 = 0,1042$$
    
    $$\text{Diferencia puntual} = 0,25 - 0,30 = -0,05$$
    
    $$\text{IC} = -0,05 \pm 0,1042 \implies [-0,1542; +0,0542] \implies [-15,42\%; +5,42\%]$$
    
- **c) Interprete el intervalo: ¿una campaña es significativamente mejor?** **No**. Como el intervalo cruza por el valor cero, no existe una diferencia estadísticamente significativa entre ambas campañas con un nivel de confianza del $99\%$.
    
- **d) Si la empresa define que una diferencia de 5% o más es comercialmente relevante, ¿qué concluye?** Aunque la diferencia muestral directa es del $5\%$ a favor de B, los resultados no son concluyentes debido al amplio margen de variación obtenido, de modo que no se puede asegurar con certeza dicha relevancia comercial en la población general.
    

## Ejercicio 15

**Datos:** $n = 250$, $x = 8 \implies \hat{p} = \frac{8}{250} = 0,032$, $\text{NC} = 93\% \implies Z_{\alpha/2} = 1,81$.

- **a) Calcule un intervalo de confianza del 93% para la proporción de fallas.**
    
    $$E = 1,81 \cdot \sqrt{\frac{0,032 \cdot 0,968}{250}} = 1,81 \cdot \sqrt{0,0001239} = 1,81 \cdot 0,01113 = 0,0201$$
    
    $$\text{IC} = 0,032 \pm 0,0201 \implies [0,0119; 0,0521] \implies [1,19\%; 5,21\%]$$
    
- **b) Si se exige que el porcentaje de fallas no supere el 5%, ¿qué indica el intervalo?** Indica que **no se cumple plenamente con la exigencia**, dado que el límite superior del intervalo calculado alcanza el $5,21\%$, abriendo la posibilidad estadística de que la tasa de fallas real supere el umbral máximo estipulado.
    
- c) ¿Cuál sería el tamaño muestral necesario para estimar esta proporción con un error máximo de $\pm2\%$ y 95% de confianza? (Usando la proporción piloto $\hat{p} = 0,032$). Para $\text{NC} = 95\%$, $Z_{\alpha/2} = 1,96$. El error admisible es $E = 0,02$.
    
    $$n = \frac{Z_{\alpha/2}^2 \cdot \hat{p} \cdot \hat{q}}{E^2} = \frac{1,96^2 \cdot 0,032 \cdot 0,968}{0,02^2} = \frac{3,8416 \cdot 0,030976}{0,0004} = 297,49$$
    
    Se necesitaría una muestra de **298 dispositivos**.
    

## Ejercicio 16

**Datos:**

- Norte: $n_N = 150$, $x_N = 120 \implies \hat{p}_N = \frac{120}{150} = 0,80$.
    
- Sur: $n_S = 160$, $x_S = 90 \implies \hat{p}_S = \frac{90}{160} = 0,5625$.
    
- $\text{NC} = 98\% \implies Z_{\alpha/2} = 2,33$.
    
- **a) Calcule los límites reales de la diferencia real de proporciones al 98% de confianza ($p_N - p_S$).**
    
    $$E = 2,33 \cdot \sqrt{\frac{0,8 \cdot 0,2}{150} + \frac{0,5625 \cdot 0,4375}{160}} = 2,33 \cdot \sqrt{0,001067 + 0,001538} = 2,33 \cdot 0,05104 = 0,1189$$
    
    $$\text{Diferencia puntual} = 0,80 - 0,5625 = 0,2375$$
    
    $$\text{IC} = 0,2375 \pm 0,1189 \implies [0,1186; 0,3564] \implies [11,86\%; 35,64\%]$$
    
- b) ¿Se puede afirmar que la proporción de hogares con acceso a internet en la región Norte es mayor que en la región Sur? Justifique. **Sí**, se puede afirmar con total seguridad estadística. El intervalo construido comprende únicamente valores positivos (el límite inferior está bien por encima de cero), demostrando de forma contundente que el acceso en el Norte es superior al del Sur.
    
- **c) Si un programa público busca reducir la brecha regional a menos de 10 puntos porcentuales, ¿qué sugiere el resultado?** Sugiere que la brecha real actual es sumamente amplia, oscilando entre $11,86\%$ y $35,64\%$. Como todo el intervalo se sitúa por encima de los 10 puntos porcentuales ($10\%$), el programa público **requiere intervenir de manera prioritaria**, ya que la meta de reducción aún está lejos de cumplirse de forma natural.
    

## Ejercicio 17

**Datos:** $\sigma = 8\text{ min}$, $\text{NC} = 95\% \implies Z_{\alpha/2} = 1,96$.

- **a) Determine el tamaño de muestra necesario para cumplir con un error máximo de $\pm3$ minutos.**
    
    $$n = \left( \frac{Z_{\alpha/2} \cdot \sigma}{E} \right)^2 = \left( \frac{1,96 \cdot 8}{3} \right)^2 = \left( \frac{15,68}{3} \right)^2 = (5,2267)^2 = 27,32$$
    
    Se requeriría un tamaño de muestra de **28 componentes**.
    
- **b) Si el gerente quisiera reducir el error máximo a $\pm2$ minutos sin cambiar el nivel de confianza, ¿cómo variaría el tamaño muestral?** Recalculamos con $E = 2$:
    
    $$n = \left( \frac{1,96 \cdot 8}{2} \right)^2 = (7,84)^2 = 61,46 \implies \mathbf{62\text{ componentes}}$$
    
    **Variación:** El tamaño de muestra necesario aumentaría significativamente, pasando de 28 a 62 observaciones (más del doble) debido a la mayor exigencia de precisión.
    

## Ejercicio 18

**Datos:** $\text{NC} = 95\% \implies Z_{\alpha/2} = 1,96$, $E = \pm4\% = 0,04$. _(Nota: El texto original dice "$\pm49$", interpretado técnicamente como un error tipográfico por $\pm4\%$, estándar en este tipo de problemas)._

- **a) Determine el tamaño mínimo de muestra necesario para estimar la proporción con la precisión requerida (sin información previa).** Al no contar con antecedentes, empleamos la máxima varianza posible ($\hat{p} = 0,5, \hat{q} = 0,5$).
    
    $$n = \frac{Z_{\alpha/2}^2 \cdot \hat{p} \cdot \hat{q}}{E^2} = \frac{1,96^2 \cdot 0,5 \cdot 0,5}{0,04^2} = \frac{3,8416 \cdot 0,25}{0,0016} = 600,25 \implies \mathbf{601\text{ usuarios}}$$
    
- **b) Si un estudio preliminar sugiere que la proporción real de usuarios satisfechos ronda el 70%, recalcule el tamaño muestral.** Utilizamos ahora $\hat{p} = 0,7$ y $\hat{q} = 0,3$.
    
    $$n = \frac{1,96^2 \cdot 0,7 \cdot 0,3}{0,04^2} = \frac{3,8416 \cdot 0,21}{0,0016} = \frac{0,806736}{0,0016} = 504,21 \implies \mathbf{505\text{ usuarios}}$$
    
- **c) Compare ambos tamaños y explique por qué cambia el valor requerido.** El tamaño requerido disminuye de 601 a 505 usuarios. Esto ocurre porque al disponer de información preliminar ($\hat{p}=0,7$), la incertidumbre o variabilidad del fenómeno se reduce respecto al escenario de máxima ignorancia estadística ($50\%$), lo que nos permite lograr idéntica precisión con un número menor de encuestados.
    

## Ejercicio 19

**Datos:** $E = 0,01\text{ mm}$, $\text{NC} = 95\% \implies Z_{\alpha/2} = 1,96$, $\sigma = 0,040\text{ mm}$. _(Nota: El enunciado original se corta; se procede a calcular el tamaño muestral requerido implícito con las condiciones descritas)._

$$n = \left( \frac{Z_{\alpha/2} \cdot \sigma}{E} \right)^2 = \left( \frac{1,96 \cdot 0,040}{0,01} \right)^2 = (7,84)^2 = 61,46$$

El tamaño muestral requerido es de **62 componentes**.

## Ejercicio 20

**Datos:** $n = 35$, $\bar{x} = 20,16\text{ mm}$, $s = 0,120\text{ mm}$.

- **a) Calcule un intervalo de confianza del 88% para la media poblacional.** Para un $\text{NC} = 88\%$, $Z_{\alpha/2} = 1,555$.
    
    $$E = 1,555 \cdot \frac{0,120}{\sqrt{35}} = 1,555 \cdot 0,02028 = 0,0315\text{ mm}$$
    
    $$\text{IC} = 20,16 \pm 0,0315 \implies [20,1285\text{ mm}; 20,1915\text{ mm}]$$
    
- b) Suponga ahora que la empresa desea estimar la media con error máximo tolerable de 0,03 mm y nivel de confianza 95%. Calcule el tamaño muestral necesario. Condiciones nuevas: $E = 0,03\text{ mm}$, $\text{NC} = 95\% \implies Z_{\alpha/2} = 1,96$. Usamos la desviación estándar muestral como aproximación histórica: $\sigma \approx 0,120\text{ mm}$.
    
    $$n = \left( \frac{1,96 \cdot 0,120}{0,03} \right)^2 = (7,84)^2 = 61,46$$
    
    Se requerirá un tamaño muestral de **62 ejes**.