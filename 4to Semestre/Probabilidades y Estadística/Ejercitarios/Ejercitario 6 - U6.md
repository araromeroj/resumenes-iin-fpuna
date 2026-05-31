Vamos a resolver paso a paso cada uno de los ejercicios de este ejercitario sobre **distribuciones muestrales**.

Para que sea sumamente fácil de seguir, utilizaremos las aproximaciones a la distribución normal estándar ($Z$) aplicando el Teorema del Límite Central y las fórmulas correspondientes para cada tipo de problema (medias, proporciones, diferencias de medias y diferencias de proporciones).

## Ejercicio 1: Distribución de la media muestral (Paquetes de datos)

**Datos:** * Distribución normal: $\mu = 3100$ bytes, $\sigma = 150$ bytes

- Muestra ($n$): 100 paquetes
    
- Error estándar de la media: $\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} = \frac{150}{\sqrt{100}} = 15$
    

a) Probabilidad de que el tamaño medio sea superior a 3130 bytes

Queremos hallar $P(\bar{X} > 3130)$. Estandarizamos a $Z$:

$$Z = \frac{3130 - 3100}{15} = \frac{30}{15} = 2$$

$$P(Z > 2) = 1 - P(Z \le 2) = 1 - 0.9772 = 0.0228$$

- **Respuesta:** **2.28%**
    

b) Probabilidad de que esté entre 3075 y 3125 bytes

Queremos hallar $P(3075 < \bar{X} < 3125)$. Estandarizamos ambos límites:

$$Z_1 = \frac{3075 - 3100}{15} = \frac{-25}{15} \approx -1.67$$

$$Z_2 = \frac{3125 - 3100}{15} = \frac{25}{15} \approx 1.67$$

$$P(-1.67 < Z < 1.67) = P(Z < 1.67) - P(Z < -1.67) = 0.9525 - 0.0475 = 0.9050$$

- **Respuesta:** **90.50%**
    

## Ejercicio 2: Diferencia de proporciones (Herramienta de automatización)

**Datos:**

- Desarrolladores (1): $p_1 = 0.28$, $n_1 = 42$
    
- Analistas de calidad (2): $p_2 = 0.25$, $n_2 = 40$
    
- Media de la diferencia: $\mu_{\hat{p}_1 - \hat{p}_2} = p_1 - p_2 = 0.28 - 0.25 = 0.03$
    
- Error estándar de la diferencia:
    
    $$\sigma_{\hat{p}_1 - \hat{p}_2} = \sqrt{\frac{p_1(1-p_1)}{n_1} + \frac{p_2(1-p_2)}{n_2}} = \sqrt{\frac{0.28(0.72)}{42} + \frac{0.25(0.75)}{40}} = \sqrt{0.0048 + 0.0046875} \approx 0.0974$$
    

Queremos la probabilidad de que la proporción de desarrolladores supere a la de analistas por al menos un 4% ($0.04$):

$$P(\hat{p}_1 - \hat{p}_2 \ge 0.04)$$

Estandarizamos:

$$Z = \frac{0.04 - 0.03}{0.0974} = \frac{0.01}{0.0974} \approx 0.10$$

$$P(Z \ge 0.10) = 1 - P(Z < 0.10) = 1 - 0.5398 = 0.4602$$

- **Respuesta:** **46.02%**
    

## Ejercicio 3: Parámetros y probabilidad de la media muestral

**Datos:**

- $\mu = 165$ GB/s, $\sigma = 8$ GB/s
    
- $n = 36$ servidores
    

a) Parámetros de la distribución de la media muestral

- Media muestral ($\mu_{\bar{x}}$): $\mu_{\bar{x}} = \mu = 165\text{ GB/s}$
    
- Desviación estándar muestral ($\sigma_{\bar{x}}$): $\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} = \frac{8}{\sqrt{36}} = \frac{8}{6} \approx 1.333\text{ GB/s}$
    

b) Probabilidad de que la velocidad media sea 167 GB/s o más

Queremos hallar $P(\bar{X} \ge 167)$.

$$Z = \frac{167 - 165}{1.333} = \frac{2}{1.333} \approx 1.50$$

$$P(Z \ge 1.50) = 1 - P(Z < 1.50) = 1 - 0.9332 = 0.0668$$

- **Respuesta:** **6.68%**
    

## Ejercicio 4: Tasa de transferencia de conexiones

**Datos:**

- Distribución normal $N(71; 7)$ MB/s $\rightarrow \mu = 71$, $\sigma = 7$
    
- $n = 4$ conexiones
    
- Error estándar: $\sigma_{\bar{x}} = \frac{7}{\sqrt{4}} = 3.5$
    

Queremos hallar $P(\bar{X} > 75)$.

$$Z = \frac{75 - 71}{3.5} = \frac{4}{3.5} \approx 1.14$$

$$P(Z > 1.14) = 1 - P(Z \le 1.14) = 1 - 0.8729 = 0.1271$$

- **Respuesta:** **12.71%**
    

## Ejercicio 5: Diferencia de medias (Algoritmos de compresión)

**Datos:**

- _Nota:_ Como el enunciado no especifica las medias poblacionales $\mu_A$ y $\mu_B$, en los problemas típicos de este estilo se evalúa el comportamiento de la diferencia asumiendo que sus medias nominales son iguales ($\mu_A - \mu_B = 0$) o que nos referimos estrictamente al incremento neto sobre el comportamiento base. Asumiremos $\mu_A - \mu_B = 0$.
    
- Algoritmo A: $\sigma_A = 1.23$ MB/s, $n_A = 35$
    
- Algoritmo B: $\sigma_B = 1.37$ MB/s, $n_B = 42$
    
- Error estándar de la diferencia:
    
    $$\sigma_{\bar{x}_A - \bar{x}_B} = \sqrt{\frac{1.23^2}{35} + \frac{1.37^2}{42}} = \sqrt{\frac{1.5129}{35} + \frac{1.8769}{42}} = \sqrt{0.04322 + 0.04469} = \sqrt{0.08791} \approx 0.2965$$
    

a) Probabilidad de que la tasa promedio de A sea mayor en 0.45 MB/s que la de B

Queremos hallar $P(\bar{X}_A - \bar{X}_B > 0.45)$.

$$Z = \frac{0.45 - 0}{0.2965} \approx 1.52$$

$$P(Z > 1.52) = 1 - P(Z \le 1.52) = 1 - 0.9357 = 0.0643$$

- **Respuesta:** **6.43%**
    

b) Probabilidad de que la diferencia esté entre 0.65 y 0.83 MB/s a favor de A

Queremos hallar $P(0.65 < \bar{X}_A - \bar{X}_B < 0.83)$.

$$Z_1 = \frac{0.65 - 0}{0.2965} \approx 2.19$$

$$Z_2 = \frac{0.83 - 0}{0.2965} \approx 2.80$$

$$P(2.19 < Z < 2.80) = P(Z < 2.80) - P(Z < 2.19) = 0.9974 - 0.9857 = 0.0117$$

- **Respuesta:** **1.17%**
    

## Ejercicio 6: Proporción muestral (Seguridad en red)

**Datos:**

- Proporción poblacional ($p$): $0.38$
    
- Muestra ($n$): 50 dispositivos
    
- Error estándar de la proporción: $\sigma_{\hat{p}} = \sqrt{\frac{p(1-p)}{n}} = \sqrt{\frac{0.38 \times 0.62}{50}} = \sqrt{\frac{0.2356}{50}} = \sqrt{0.004712} \approx 0.0686$
    

Se decide separar los grupos si la proporción muestral supera el 19% ($0.19$). Queremos hallar $P(\hat{p} > 0.19)$.

$$Z = \frac{0.19 - 0.38}{0.0686} = \frac{-0.19}{0.0686} \approx -2.77$$

$$P(Z > -2.77) = P(Z < 2.77) = 0.9972$$

- **Respuesta:** **99.72%** (Es sumamente probable que se haga la separación).
    

## Ejercicio 7: Duración de baterías de móviles

**Datos:**

- $\mu = 34.5$ horas, $\sigma = 6.9$ horas
    
- $n = 36$ teléfonos
    
- Error estándar: $\sigma_{\bar{x}} = \frac{6.9}{\sqrt{36}} = \frac{6.9}{6} = 1.15$
    

a) Probabilidad de que la media esté entre 32 y 33.5 horas

$$Z_1 = \frac{32 - 34.5}{1.15} = \frac{-2.5}{1.15} \approx -2.17$$

$$Z_2 = \frac{33.5 - 34.5}{1.15} = \frac{-1}{1.15} \approx -0.87$$

$$P(-2.17 < Z < -0.87) = P(Z < -0.87) - P(Z < -2.17) = 0.1922 - 0.0150 = 0.1772$$

- **Respuesta:** **17.72%**
    

b) Probabilidad de que sea mayor de 38 horas

$$Z = \frac{38 - 34.5}{1.15} = \frac{3.5}{1.15} \approx 3.04$$

$$P(Z > 3.04) = 1 - P(Z \le 3.04) = 1 - 0.9988 = 0.0012$$

- **Respuesta:** **0.12%**
    

## Ejercicio 8: Servicio de atención al cliente

**Datos:**

- $\mu = 10$ minutos, $\sigma = 2$ minutos
    

a) Probabilidad de que el tiempo medio no supere los 9 minutos ($n = 25$)

- $\sigma_{\bar{x}} = \frac{2}{\sqrt{25}} = 0.4$ Queremos hallar $P(\bar{X} \le 9)$.
    
    $$Z = \frac{9 - 10}{0.4} = \frac{-1}{0.4} = -2.5$$
    

$$P(Z \le -2.5) = 0.0062$$

- **Respuesta:** **0.62%**
    

b) Distribución de la media muestral si $n = 64$

La distribución de la media muestral sigue una distribución normal:

$$\bar{X} \sim N(\mu_{\bar{x}}, \sigma_{\bar{x}})$$

- $\mu_{\bar{x}} = \mu = 10\text{ minutos}$
    
- $\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} = \frac{2}{\sqrt{64}} = \frac{2}{8} = 0.25\text{ minutos}$
    
- **Respuesta:** **$\bar{X} \sim N(10; 0.25)$**
    

## Ejercicio 9: Vida útil de componentes electrónicos

**Datos:**

- $\mu = 76$ mil horas, $\sigma = 10$ mil horas
    
- $n = 25$ componentes
    
- $\sigma_{\bar{x}} = \frac{10}{\sqrt{25}} = 2$
    

a) Probabilidad de que la vida útil media sea inferior a 74 mil horas

Queremos hallar $P(\bar{X} < 74)$.

$$Z = \frac{74 - 76}{2} = \frac{-2}{2} = -1$$

$$P(Z < -1) = 0.1587$$

- **Respuesta:** **15.87%**
    

b) Valor de la vida útil promedio que deja por debajo al 80%

Queremos encontrar un valor $k$ tal que $P(\bar{X} < k) = 0.80$. Buscando en la tabla normal estándar, el valor $Z$ que corresponde a una probabilidad acumulada de $0.80$ es aproximadamente $Z = 0.84$.

Despejamos de la fórmula de estandarización:

$$k = \mu + (Z \times \sigma_{\bar{x}}) = 76 + (0.84 \times 2) = 76 + 1.68 = 77.68$$

- **Respuesta:** **77.68 mil horas**
    

## Ejercicio 10: Precisión de calibración de sensores

**Datos:**

- $\mu = 162$ unidades, $\sigma^2 = 144 \rightarrow \sigma = \sqrt{144} = 12$ unidades
    
- $n = 100$ sensores
    
- $\sigma_{\bar{x}} = \frac{12}{\sqrt{100}} = 1.2$
    

a) Probabilidad de que la media de error esté entre 159 y 165 unidades

$$Z_1 = \frac{159 - 162}{1.2} = \frac{-3}{1.2} = -2.5$$

$$Z_2 = \frac{165 - 162}{1.2} = \frac{3}{1.2} = 2.5$$

$$P(-2.5 < Z < 2.5) = P(Z < 2.5) - P(Z < -2.5) = 0.9938 - 0.0062 = 0.9876$$

- **Respuesta:** **98.76%**
    

b) Probabilidad de que la media de error supere las 164 unidades

$$Z = \frac{164 - 162}{1.2} = \frac{2}{1.2} \approx 1.67$$

$$P(Z > 1.67) = 1 - P(Z \le 1.67) = 1 - 0.9525 = 0.0475$$

- **Respuesta:** **4.75%**
    

## Ejercicio 11: Muestras repetidas de sensores de temperatura

**Datos:**

- $\mu = 2.50$, $\sigma = 0.80$
    
- $n = 30$ sensores
    
- $\sigma_{\bar{x}} = \frac{0.80}{\sqrt{30}} \approx 0.1461$
    
- Número total de muestras tomadas ($N$): 150 muestras
    

a) ¿Cuántas de las medias muestrales estarán entre 2.10 y 2.90?

Estandarizamos los límites:

$$Z_1 = \frac{2.10 - 2.50}{0.1461} = \frac{-0.40}{0.1461} \approx -2.74$$

$$Z_2 = \frac{2.90 - 2.50}{0.1461} = \frac{0.40}{0.1461} \approx 2.74$$

$$P(-2.74 < Z < 2.74) = 0.9969 - 0.0031 = 0.9938$$

Multiplicamos la probabilidad por el número de muestras ($N=150$):

$$\text{Cantidad} = 150 \times 0.9938 \approx 149.07$$

- **Respuesta:** Aproximadamente **149 medias muestrales**.
    

b) ¿Cuántas de las medias muestrales estarán por debajo de 2.20?

$$Z = \frac{2.20 - 2.50}{0.1461} = \frac{-0.30}{0.1461} \approx -2.05$$

$$P(Z < -2.05) = 0.0202$$

Multiplicamos por las 150 muestras:

$$\text{Cantidad} = 150 \times 0.0202 = 3.03$$

- **Respuesta:** Aproximadamente **3 medias muestrales**.
    

## Ejercicio 12: Comparación de sensores Tipo A y Tipo B

**Datos:**

- Tipo A: $\mu_A = 120$ ms, $\sigma_A = 8$ ms, $n_A = 40$
    
- Tipo B: $\mu_B = 125$ ms, $\sigma_B = 10$ ms, $n_B = 50$
    
- Media de la diferencia ($\mu_{\bar{x}_A - \bar{x}_B}$): $120 - 125 = -5$ ms
    
- Error estándar de la diferencia:
    
    $$\sigma_{\bar{x}_A - \bar{x}_B} = \sqrt{\frac{8^2}{40} + \frac{10^2}{50}} = \sqrt{\frac{64}{40} + \frac{100}{50}} = \sqrt{1.6 + 2} = \sqrt{3.6} \approx 1.8974\text{ ms}$$
    

a) Probabilidad de que Tipo A tenga una media menor que Tipo B

Esto equivale a decir que la diferencia es menor que cero: $P(\bar{X}_A - \bar{X}_B < 0)$.

$$Z = \frac{0 - (-5)}{1.8974} = \frac{5}{1.8974} \approx 2.64$$

$$P(Z < 2.64) = 0.9959$$

- **Respuesta:** **99.59%**
    

b) Probabilidad de que Tipo A sea al menos 3 ms más rápido que Tipo B

"Ser más rápido" en tiempo de respuesta significa gastar **menos** milisegundos. Por lo tanto, el tiempo de A debe ser menor o igual al de B menos 3 ms ($\bar{X}_A \le \bar{X}_B - 3$), lo que se traduce en: $P(\bar{X}_A - \bar{X}_B \le -3)$.

$$Z = \frac{-3 - (-5)}{1.8974} = \frac{2}{1.8974} \approx 1.05$$

$$P(Z \le 1.05) = 0.8531$$

- **Respuesta:** **85.31%**
    

c) Probabilidad de que la diferencia esté entre -1 y +1 ms

Queremos hallar $P(-1 < \bar{X}_A - \bar{X}_B < 1)$.

$$Z_1 = \frac{-1 - (-5)}{1.8974} = \frac{4}{1.8974} \approx 2.11$$

$$Z_2 = \frac{1 - (-5)}{1.8974} = \frac{6}{1.8974} \approx 3.16$$

$$P(2.11 < Z < 3.16) = P(Z < 3.16) - P(Z < 2.11) = 0.9992 - 0.9826 = 0.0166$$

- **Respuesta:** **1.66%**
    

## Ejercicio 13: Proporción de fallas en microchips

**Datos:**

- Tipo A: $p_A = 0.04$, $n_A = 200$
    
- Tipo B: $p_B = 0.06$, $n_B = 300$
    
- Media de la diferencia: $\mu_{\hat{p}_A - \hat{p}_B} = 0.04 - 0.06 = -0.02$
    
- Error estándar de la diferencia:
    
    $$\sigma_{\hat{p}_A - \hat{p}_B} = \sqrt{\frac{0.04(0.96)}{200} + \frac{0.06(0.94)}{300}} = \sqrt{0.000192 + 0.000188} = \sqrt{0.00038} \approx 0.0195$$
    

a) Probabilidad de que la proporción en A sea menor que en B

Equivale a $P(\hat{p}_A - \hat{p}_B < 0)$.

$$Z = \frac{0 - (-0.02)}{0.0195} = \frac{0.02}{0.0195} \approx 1.03$$

$$P(Z < 1.03) = 0.8485$$

- **Respuesta:** **84.85%**
    

b) Probabilidad de que la diferencia en proporciones de fallas sea al menos 0.03

Asumiendo la diferencia absoluta o en el orden estipulado $P(\hat{p}_A - \hat{p}_B \ge 0.03)$:

$$Z = \frac{0.03 - (-0.02)}{0.0195} = \frac{0.05}{0.0195} \approx 2.56$$

$$P(Z \ge 2.56) = 1 - 0.9948 = 0.0052$$

- **Respuesta:** **0.52%**
    

c) Probabilidad de que la diferencia esté dentro de $\pm0.02$

Queremos hallar $P(-0.02 \le \hat{p}_A - \hat{p}_B \le 0.02)$.

$$Z_1 = \frac{-0.02 - (-0.02)}{0.0195} = 0$$

$$Z_2 = \frac{0.02 - (-0.02)}{0.0195} = \frac{0.04}{0.0195} \approx 2.05$$

$$P(0 \le Z \le 2.05) = P(Z \le 2.05) - P(Z \le 0) = 0.9798 - 0.5000 = 0.4798$$

- **Respuesta:** **47.98%**
    

## Ejercicio 14: Fallas en la interfaz de aplicaciones móviles

**Datos:**

- Versión A: $p_A = 0.30$, $n_A = 150$
    
- Versión B: $p_B = 0.25$, $n_B = 200$
    
- Media de la diferencia: $\mu_{\hat{p}_A - \hat{p}_B} = 0.30 - 0.25 = 0.05$
    
- Error estándar de la diferencia:
    
    $$\sigma_{\hat{p}_A - \hat{p}_B} = \sqrt{\frac{0.30(0.70)}{150} + \frac{0.25(0.75)}{200}} = \sqrt{0.0014 + 0.0009375} = \sqrt{0.0023375} \approx 0.0483$$
    

a) Probabilidad de que la proporción en A sea mayor que en B

Equivale a $P(\hat{p}_A - \hat{p}_B > 0)$.

$$Z = \frac{0 - 0.05}{0.0483} = \frac{-0.05}{0.0483} \approx -1.04$$

$$P(Z > -1.04) = P(Z < 1.04) = 0.8508$$

- **Respuesta:** **85.08%**
    

b) Probabilidad de que la diferencia esté entre -0.02 y 0.05

Queremos hallar $P(-0.02 < \hat{p}_A - \hat{p}_B < 0.05)$.

$$Z_1 = \frac{-0.02 - 0.05}{0.0483} = \frac{-0.07}{0.0483} \approx -1.45$$

$$Z_2 = \frac{0.05 - 0.05}{0.0483} = 0$$

$$P(-1.45 < Z < 0) = P(Z < 0) - P(Z < -1.45) = 0.5000 - 0.0735 = 0.4265$$

- **Respuesta:** **42.65%**
    

## Ejercicio 15: Abandono de carrito de compras

**Datos:**

- Proporción poblacional ($p$): $0.15$
    
- Muestra ($n$): 120 clientes
    
- Error estándar: $\sigma_{\hat{p}} = \sqrt{\frac{0.15(0.85)}{120}} = \sqrt{\frac{0.1275}{120}} = \sqrt{0.0010625} \approx 0.0326$
    

a) Probabilidad de que menos del 10% de la muestra abandone el carrito

Queremos hallar $P(\hat{p} < 0.10)$.

$$Z = \frac{0.10 - 0.15}{0.0326} = \frac{-0.05}{0.0326} \approx -1.53$$

$$P(Z < -1.53) = 0.0630$$

- **Respuesta:** **6.30%**
    

b) Probabilidad de que la proporción esté entre 12% y 18%

Queremos hallar $P(0.12 < \hat{p} < 0.18)$.

$$Z_1 = \frac{0.12 - 0.15}{0.0326} = \frac{-0.03}{0.0326} \approx -0.92$$

$$Z_2 = \frac{0.18 - 0.15}{0.0326} = \frac{0.03}{0.0326} \approx 0.92$$

$$P(-0.92 < Z < 0.92) = P(Z < 0.92) - P(Z < -0.92) = 0.8212 - 0.1788 = 0.6424$$

- **Respuesta:** **64.24%**