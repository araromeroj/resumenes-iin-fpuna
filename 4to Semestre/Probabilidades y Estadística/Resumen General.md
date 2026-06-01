A continuación, presento la **Ficha de Fórmulas Final**, un compendio analítico y operativo de todas las ecuaciones fundamentales desarrolladas a lo largo de las 8 unidades del programa académico. Esta guía sigue estrictamente la estructura pedagógica institucional y resalta las consideraciones críticas para asegurar el éxito en las evaluaciones.

## UNIDAD 1: Estadística Descriptiva

### 1. Media Ametralladora Muestral ($\bar{x}$) para datos no agrupados

$$\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}$$

- **Variables y Unidades:** * $\bar{x}$: Media o promedio de la muestra (unidades de la variable: kg, m, $, etc.).
    
    - $x_i$: Valor individual de cada observación numérica.
        
    - $n$: Tamaño total de la muestra o número de observaciones.
    
- **Aplicación:** Identificar frases como "calcular el promedio", "valor medio" o "estatura promedio" sobre un listado directo de datos numéricos aislados.

### 2. Varianza Muestral ($s^2$) para datos no agrupados

$$s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n - 1}$$

- **Variables y Unidades:**
    
    - $s^2$: Varianza de la muestra (unidades elevadas al cuadrado, ej: $\text{kg}^2$, $\$^2$).
    
- **Aplicación:** Medición de la dispersión de datos crudos respecto a su centro. Clave: frases como "determinar la varianza".    

### 3. Desviación Estándar Muestral ($s$)

$$s = \sqrt{s^2}$$

- **Variables y Unidades:**
    
    - $s$: Desviación típica o estándar muestral (unidades lineales de la variable original).
    
- **Aplicación:** Cuando se pide reportar el nivel de dispersión en el formato lineal de los datos.

### 4. Marca de Clase ($x_i$) para datos agrupados

$$x_i = \frac{L_i + L_s}{2}$$

- **Variables y Unidades:**
    
    - $x_i$: Punto medio o marca de clase del intervalo.
        
    - $L_i, L_s$: Límite inferior y límite superior de una clase en una tabla de frecuencias.
    
- **Aplicación:** Paso obligatorio previo al cálculo de medias y varianzas si los datos están tabulados en intervalos.

>[!warning] Detalles Clave y Errores Comunes
>- **Denominador de la varianza ($n-1$):** Para datos muestrales, divide rigurosamente por $n-1$ (grados de libertad), no por $n$. Dividir por $n$ se reserva exclusivamente para censos o poblaciones completas.

---
## UNIDAD 2: Probabilidad

### 1. Enfoque Clásico de Probabilidad (Regla de Laplace)

$$P(A) = \frac{\text{Casos Favorables}}{\text{Casos Posibles}}$$

- **Variables y Unidades:**
    
    - $P(A)$: Probabilidad de ocurrencia del evento $A$ (adimensional, de 0 a 1).
    
- **Aplicación:** Experimentos donde todos los resultados tienen la misma probabilidad de ocurrir (ej: lanzar dados, extraer cartas).

### 2. Regla General de la Adición (Eventos no excluyentes)

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

- **Variables y Unidades:**
    
    - $P(A \cup B)$: Probabilidad de que ocurra el evento $A$, el evento $B$ o ambos (conjunción "O").
        
    - $P(A \cap B)$: Probabilidad de la intersección o simultaneidad (conjunción "Y").
    
- **Aplicación:** Enunciados que pregunten por la probabilidad de "A o B", donde ambos pueden suceder al mismo tiempo (ej: "que sea mujer o que esté aprobada").

>[!warning] Detalles Clave y Errores Comunes
>- **Axioma Fundamental:** Ninguna probabilidad calculada puede ser menor que 0 ni mayor que 1 ($0 \le P(A) \le 1$). Si tu resultado sale de este margen, hay un error algebraico.
>- **Eventos Mutuamente Excluyentes:** Si el problema aclara que los eventos no pueden ocurrir juntos, $P(A \cap B) = 0$, simplificando la ecuación a $P(A \cup B) = P(A) + P(B)$.

---
## UNIDAD 3: Variables Aleatorias y Distribuciones de Probabilidad

### 1. Valor Esperado (Esperanza Matemática, $\mu$) para variables discretas

$$\mu = E(X) = \sum_{i=1}^{k} x_i \cdot P(X = x_i)$$

- **Variables y Unidades:**
    
    - $\mu$ o $E(X)$: Media teórica a largo plazo de la v.a.
        
    - $x_i$: Valor numérico que asume la variable.
        
    - $P(X = x_i)$: Probabilidad exacta asociada a dicho valor.
    
- **Aplicación:** Enunciados discretos donde se solicita "el número esperado de...", "el promedio teórico" o la "esperanza de ganancia".

### 2. Varianza Operativa de una Variable Discreta

$$\sigma^2 = V(X) = E(X^2) - [E(X)]^2 = \left( \sum_{i=1}^{k} x_i^2 \cdot P(X = x_i) \right) - \mu^2$$

- **Variables y Unidades:**
    
    - $\sigma^2$: Varianza de la distribución teórica.
    
- **Aplicación:** Método más ágil para calcular la dispersión teórica a partir de una tabla de distribución.

>[!warning] Detalles Clave y Errores Comunes
>- **Condición de Cierre:** Verifica siempre que la suma de todas las probabilidades de la tabla sea exactamente igual a 1 ($\sum P(X = x_i) = 1$).
>- **Distinción Crítica:** No confundas $E(X^2)$ (elevar cada $x_i$ al cuadrado antes de multiplicar por su probabilidad) con $[E(X)]^2$ (elevar el resultado final de la media al cuadrado).
>- **Variables Continuas:** Recuerda que para cualquier punto exacto en variables continuas, la probabilidad es cero: $P(X = c) = 0$.

---
## UNIDAD 4: Distribuciones Discretas de Probabilidad

### 1. Función de Probabilidad Binomial

$$P(X = x) = \binom{n}{x} \cdot p^x \cdot q^{n-x}$$

- **Variables y Unidades:**
    
    - $n$: Número fijo de ensayos independientes.
        
    - $p$: Probabilidad constante de éxito.
        
    - $q$: Probabilidad de fracaso ($1 - p$).
        
    - $x$: Cantidad de éxitos deseados ($0, 1, \dots, n$).
    
- **Aplicación:** Muestras con un número cerrado de repeticiones donde cada unidad es clasificada de forma dicotómica (ej: defectuoso o no defectuoso).
    
- **Parámetros:** $\mu = n \cdot p$ ; $\sigma^2 = n \cdot p \cdot q$.

### 2. Función de Probabilidad de Poisson

$$P(X = x) = \frac{e^{-\lambda} \cdot \lambda^x}{x!}$$

- **Variables y Unidades:**
    
    - $\lambda$: Tasa media de ocurrencia esperada en un intervalo específico.
        
    - $e$: Constante de base natural ($\approx 2.71828$).
    
- **Aplicación:** Conteo de eventos independientes a lo largo de una unidad continua de tiempo o espacio (ej: "accidentes por semana", "bacterias por volumen").
    
- **Parámetros:** $\mu = \lambda$ ; $\sigma^2 = \lambda$.

### 3. Función de Probabilidad Geométrica

$$P(X = x) = q^{x-1} \cdot p$$

- **Variables y Unidades:**
    
    - $x$: Ensayo ordinal en el que se observa el primer éxito ($x = 1, 2, 3, \dots$).
    
- **Aplicación:** Enunciados donde el experimento continúa sucesivamente y se detiene en el instante exacto en que se logra el "primer éxito".
    
- **Parámetros:** $\mu = \frac{1}{p}$.

>[!warning] Detalles Clave y Errores Comunes
>- **Ajuste Proporcional de Lambda ($\lambda$):** Adapta siempre $\lambda$ al intervalo exacto de la pregunta. Si ocurren 3 llamadas por minuto y te preguntan por un intervalo de 5 minutos, utiliza un $\lambda$ corregido de $3 \times 5 = 15$.  
>- **Estrategia del Complemento:** Para expresiones como "al menos uno", calcula $P(X \ge 1) = 1 - P(X = 0)$.  
>- **Rango de la Geométrica:** El valor mínimo de la variable es $x=1$. No existe el escenario $x=0$ en este modelo.

---
## UNIDAD 5: Distribuciones Continuas de Probabilidad

### 1. Probabilidad Uniforme Continua

$$P(x_1 \le X \le x_2) = \frac{x_2 - x_1}{b - a}$$

- **Variables y Unidades:**
    
    - $a, b$: Límites inferior y superior absolutos del intervalo continuo.
        
    - $x_1, x_2$: Subintervalo específico analizado.
    
- **Aplicación:** Variables en las que se detalla explícitamente que la densidad es constante o uniforme sobre un rango cerrado.
    
- **Parámetros:** $\mu = \frac{a+b}{2}$ ; $\sigma^2 = \frac{(b-a)^2}{12}$.

### 2. Probabilidad Exponencial Acumulada

$$P(X \le x) = 1 - e^{-\alpha \cdot x} \quad \Longrightarrow \quad P(X > x) = e^{-\alpha \cdot x}$$

- **Variables y Unidades:**
    
    - $\alpha$: Tasa promedio de eventos (inverso de la duración promedio $\mu$).
    
- **Aplicación:** Medición de tiempos de espera o duraciones entre eventos sucesivos (ej: tiempo transcurrido hasta que falle una máquina).

### 3. Transformación Normal Estándar ($Z$)

$$Z = \frac{X - \mu}{\sigma}$$

- **Variables y Unidades:**
    
    - $Z$: Valor estandarizado (adimensional, buscar con 2 decimales en la tabla).
        
    - $X$: Valor real medido de la variable.
        
    - $\mu, \sigma$: Media y desviación estándar de la población.
    
- **Aplicación:** Problemas con datos de perfil acampanado/normal para hallar probabilidades usando la tabla normal estándar.

>[!warning] Detalles Clave y Errores Comunes
>- **Inversión de Tasa en la Exponencial:** Si el enunciado menciona que "la atención dura en promedio 10 minutos" ($\mu = 10$), el parámetro es $\alpha = 1/10 = 0.1$. No uses la duración de forma directa como tasa.
>- **Corrección por Continuidad:** Al aproximar una Binomial a una Normal (si $n \cdot p \ge 5$ y $n \cdot q \ge 5$), suma o resta $0.5$ al valor discreto antes de estandarizar para compensar las barras (ej: $P(X \le 10) \rightarrow P(X_{\text{normal}} \le 10.5)$).


---
## UNIDAD 6: Distribuciones Muestrales

### 1. Estandarización de la Media Muestral ($\bar{x}$) para Poblaciones Infinitas

$$Z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}}$$

- **Variables y Unidades:**
    
    - $\bar{x}$: Promedio de la muestra analizada.
        
    - $\mu, \sigma$: Parámetros originales de la población.
        
    - $n$: Tamaño del grupo o muestra extraída.
    
- **Aplicación:** Preguntas sobre la probabilidad de que el _promedio de una muestra_ cumpla cierta condición.

### 2. Estandarización de la Media con Factor de Corrección para Poblaciones Finitas

$$Z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}} \cdot \sqrt{\frac{N - n}{N - 1}}}$$

- **Variables y Unidades:**
    
    - $N$: Tamaño absoluto de la población total cerrada.
    
- **Aplicación:** Utilizar únicamente cuando el tamaño de la población $N$ es conocido y la fracción de muestreo supera el 5% ($\frac{n}{N} > 0.05$).

### 3. Estandarización de la Proporción Muestral ($\bar{p}$)

$$Z = \frac{\bar{p} - p}{\sqrt{\frac{p \cdot q}{n}}}$$

- **Variables y Unidades:**
    
    - $\bar{p}$: Proporción de éxitos observada en la muestra ($x/n$).
        
    - $p, q$: Proporciones correspondientes en el universo poblacional de origen.
    
- **Aplicación:** Preguntas probabilísticas enfocadas en evaluar tasas o porcentajes de una muestra aleatoria extraída.

>[!warning] Detalles Clave y Errores Comunes
>- **Olvidar dividir por la raíz de $n$:** Al analizar una media muestral, el denominador correcto es el error estándar ($\sigma/\sqrt{n}$), nunca uses simplemente $\sigma$.  
>- **Teorema del Límite Central (TLC):** Si la población de origen no es normal o es desconocida, puedes justificar formalmente el uso de la campana normal de $Z$ siempre y cuando la muestra sea grande ($n \ge 30$).

---
## UNIDAD 7: Intervalos de Confianza

### 1. Intervalo de Confianza para la Media Poblacional ($\mu$) - Muestras Grandes

$$\bar{x} \pm Z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}$$

- **Variables y Unidades:**
    
    - $Z_{\alpha/2}$: Valor crítico obtenido mediante búsqueda inversa de área en la tabla normal.
        
    - $\sigma$: Desviación estándar de la población. Si es desconocida y $n \ge 30$, aproximar usando la desviación estándar muestral $s$.
    
- **Aplicación:** Estimación de un rango de valores para el promedio real de un universo a partir de una muestra grande.

### 2. Coeficiente Crítico Especial por Semisuma

$$\text{Si Confianza} = 99\% \ \rightarrow \ \frac{0.99}{2} = 0.4950 \ \rightarrow \ Z_{\alpha/2} = \pm 2.575$$

- **Aplicación:** Criterio formal obligatorio dictado por los materiales institucionales ante empates de área simétrica en el cuerpo de la tabla normal.

### 3. Intervalo de Confianza para la Proporción Poblacional ($p$)

$$\hat{p} \pm Z_{\alpha/2} \cdot \sqrt{\frac{\hat{p} \cdot \hat{q}}{n}}$$

- **Variables y Unidades:**
    
    - $\hat{p}, \hat{q}$: Proporciones muestrales complementarias en formato decimal ($\hat{q} = 1 - \hat{p}$).
    
- **Aplicación:** Definir el intervalo de incertidumbre para un porcentaje poblacional bajo estudio.

### 4. Intervalo para Diferencia de Medias ($\mu_1 - \mu_2$)

$$(\bar{x}_1 - \bar{x}_2) \pm Z_{\alpha/2} \cdot \sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}$$

- **Aplicación:** Enunciados donde se busca medir el contraste entre el promedio de dos poblaciones independientes.

>[!warning] Detalles Clave y Errores Comunes
>- **Manejo de Varianzas vs Desviaciones:** Si los datos del examen te dan la desviación típica, elécvala al cuadrado en la fórmula de diferencia de medias ($\sigma^2$). Si te dan la varianza de forma directa, insértala sin volver a elevarla.
>- **Formato Decimal Riguroso:** Las proporciones bajo el radical de la fórmula de proporciones deben operarse en números decimales (ej: usar $0.12$, nunca $12\%$).

---
## UNIDAD 8: Pruebas de Hipótesis

### 1. Estadístico de Prueba para una Media ($\mu$)

$$Z_{\text{calc}} = \frac{\bar{x} - \mu_0}{\frac{\sigma}{\sqrt{n}}}$$

- **Variables y Unidades:**
    
    - $Z_{\text{calc}}$: Valor numérico estandarizado obtenido empíricamente de la muestra.
        
    - $\mu_0$: Valor numérico del parámetro asumido bajo la validez de la hipótesis nula $H_0$.
    
- **Aplicación:** Evaluar si la media poblacional real difiere, supera o es inferior a una especificación teórica.

### 2. Estadístico de Prueba para una Proporción ($p$)

$$Z_{\text{calc}} = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0 \cdot q_0}{n}}}$$

- **Variables y Unidades:**
    
    - $p_0, q_0$: Valores numéricos de proporción propuestos en el enunciado para la hipótesis nula.
    
- **Aplicación:** Contrastar si el porcentaje real de un atributo difiere del estándar teórico.

### 3. Criterio de Decisión General

$$\text{Si } Z_{\text{calc}} \text{ cae en la zona de rechazo} \ \rightarrow \ \text{Rechazar } H_0$$

$$\text{Si } Z_{\text{calc}} \text{ cae en la zona de aceptación} \ \rightarrow \ \text{No Rechazar } H_0$$

- **Aplicación:** Paso fundamental para contrastar la hipótesis matemática con los valores críticos de la tabla.

>[!warning] Detalles Clave y Errores Comunes
>- **Asignación exclusiva del signo de igualdad:** La Hipótesis Nula ($H_0$) debe contener obligatoriamente la condición de igualdad o inclusión ($=$, $\le$, $\ge$). La Hipótesis Alternativa ($H_1$) recoge la desigualdad estricta ($\neq$, $<$, $>$) y determina las colas de la prueba.
>- **Error Estándar de la Proporción:** Para calcular el denominador en la prueba de hipótesis de proporciones, usa obligatoriamente el valor teórico $p_0$, no el valor de la muestra $\hat{p}$.
>- **Signo algebraico del numerador:** Mantén estrictamente el orden $(\bar{x} - \mu_0)$ o $(\hat{p} - p_0)$. Si el resultado es negativo, el valor de $Z_{\text{calc}}$ reflejará su signo real, lo cual es crítico para las pruebas de cola izquierda.

