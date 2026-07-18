Este concepto e información estructurada pertenecen de forma exclusiva a la **Unidad 4: Distribuciones Discretas de Probabilidad** (basado estrictamente en los materiales de lectura institucionales proporcionados).

## Síntesis Teórica Detallada

Las distribuciones discretas de probabilidad son modelos matemáticos teóricos que describen el comportamiento de variables aleatorias discretas asociadas a experimentos cuyos resultados se derivan de procesos de conteo. En esta unidad se analizan las estructuras analíticas de tres modelos fundamentales: la Distribución Binomial, la Distribución de Poisson y la Distribución Geométrica.

### 1. Proceso y Distribución Binomial

- **Definición del Proceso de Bernoulli:** Es un experimento aleatorio que cumple de manera rigurosa con las siguientes condiciones:
    
    - El experimento consiste en una serie de $n$ ensayos u observaciones idénticas y fijadas de antemano.
        
    - Cada ensayo arroja de forma exclusiva uno de dos resultados posibles mutuamente excluyentes, denominados convencionalmente **Éxito** o **Fracaso**.
        
    - La probabilidad de obtener un éxito se denota por $p$ y permanece estrictamente constante de un ensayo a otro. La probabilidad de fracaso se denota por $q$, donde de forma obligatoria $q = 1 - p$.
        
    - Todos los ensayos de la serie son estadísticamente independientes entre sí, lo que implica que el resultado de cualquier observación particular no altera en absoluto las probabilidades de los ensayos subsecuentes.
    
- **Distribución Binomial:** Es la distribución de probabilidad de la variable aleatoria discreta $X$, que se define formalmente como el número total de éxitos obtenidos al realizar los $n$ ensayos independientes de un proceso de Bernoulli.


### 2. Proceso y Distribución de Poisson

- **Naturaleza de la Distribución:** Se utiliza para modelar situaciones donde la variable aleatoria discreta representa el número de ocurrencias de un evento determinado durante un intervalo continuo de tiempo, espacio, volumen o línea recta.
    
- **Propiedades del Proceso de Poisson:**
    
    - La probabilidad de que ocurra un evento en un intervalo muy pequeño es proporcional a la longitud de dicho intervalo.
        
    - La probabilidad de que ocurran dos o más eventos en un intervalo extremadamente pequeño es insignificante (tiende a cero).
        
    - El número de eventos que ocurren en un intervalo dado es completamente independiente del número de eventos que suceden en cualquier otro intervalo disjunto.
    
- **Parámetro Lambda ($\lambda$):** Representa el promedio o tasa media de ocurrencias del evento por unidad de medida base seleccionada (tiempo, área, volumen).


### 3. Proceso y Distribución Geométrica

- **Naturaleza de la Distribución:** Al igual que la Binomial, se fundamenta en una sucesión de ensayos independientes de Bernoulli con probabilidad constante de éxito $p$.
    
- **Definición de la Variable Aleatoria:** En el modelo geométrico, los ensayos se repiten de forma sucesiva e indefinida hasta que se observa por primera vez el primer éxito del experimento. La variable aleatoria $X$ cuenta estrictamente el número de ensayos necesarios para alcanzar dicho primer éxito.

---
## Guía de Fórmulas y Aplicación

### 1. Función de Probabilidad Binomial

$$P(X = x) = \binom{n}{x} \cdot p^x \cdot q^{n-x} = \frac{n!}{x!(n-x)!} \cdot p^x \cdot (1-p)^{n-x}$$

- **Significado de variables:**
    
    - $P(X = x)$: Probabilidad exacta de obtener un número determinado $x$ de éxitos.
        
    - $n$: Número total de ensayos u observaciones fijas (entero positivo).
        
    - $x$: Número de éxitos deseados en los $n$ ensayos ($x = 0, 1, 2, \dots, n$).
        
    - $p$: Probabilidad de éxito en un único ensayo (valor real entre 0 y 1).
        
    - $q$ o $(1-p)$: Probabilidad de fracaso en un único ensayo.
        
    - $\binom{n}{x}$: Coeficiente combinatorio que calcula las maneras de ordenar los éxitos.
    
- **¿Cuándo utilizarla?:** En problemas con un número fijo y explícito de repeticiones independientes ($n$) donde cada elemento individual solo puede estar clasificado en dos estados posibles (ej. defectuoso o no defectuoso, aprueba o reprueba, marca o no marca).


### 2. Propiedades de la Distribución Binomial (Parámetros)

$$\text{Media (Esperanza): } \mu = E(X) = n \cdot p$$

$$\text{Varianza: } \sigma^2 = V(X) = n \cdot p \cdot q$$

$$\text{Desviación Típica: } \sigma = \sqrt{n \cdot p \cdot q}$$

- **¿Cuándo utilizarla?:** Cuando el enunciado pide de forma directa calcular el "valor esperado", el "promedio a largo plazo", la "varianza" o la "dispersión estándar" de éxitos en un contexto binomial, sin necesidad de calcular probabilidades puntuales primero.


### 3. Función de Probabilidad de Poisson

$$P(X = x) = \frac{e^{-\lambda} \cdot \lambda^x}{x!}$$

- **Significado de variables:**
    
    - $P(X = x)$: Probabilidad de observar exactamente $x$ eventos en el intervalo establecido.
        
    - $\lambda$ (Lambda): Promedio o tasa media de ocurrencias esperadas dentro del intervalo de interés (número real positivo).
        
    - $x$: Cantidad de ocurrencias del evento bajo estudio ($x = 0, 1, 2, \dots$).
        
    - $e$: Constante matemática base de los logaritmos naturales ($\approx 2.71828$).
    
- **¿Cuándo utilizarla?:** Se identifica por la mención explícita de una tasa promedio de ocurrencia asociada a una unidad de medida continua (ej. "llegan en promedio 3 clientes por hora", "se registran 2 defectos por metro de cable").


### 4. Propiedades de la Distribución de Poisson (Parámetros)

$$\text{Media (Esperanza): } \mu = E(X) = \lambda$$

$$\text{Varianza: } \sigma^2 = V(X) = \lambda$$

$$\text{Desviación Típica: } \sigma = \sqrt{\lambda}$$

- **¿Cuándo utilizarla?:** Cuando se solicita evaluar la variabilidad o el valor central teórico en un proceso de Poisson. Destaca la propiedad matemática de que su media y su varianza son numéricamente idénticas.    

### 5. Función de Probabilidad Geométrica

$$P(X = x) = q^{x-1} \cdot p = (1-p)^{x-1} \cdot p$$

- **Significado de variables:**
    
    - $P(X = x)$: Probabilidad de que el primer éxito ocurra precisamente en el ensayo número $x$.
        
    - $p$: Probabilidad constante de éxito en cada ensayo individual.
        
    - $q$ o $(1-p)$: Probabilidad constante de fracaso en cada ensayo individual.
        
    - $x$: El número ordinal del ensayo en el cual se consigue el primer éxito ($x = 1, 2, 3, \dots$).
    
- **¿Cuándo utilizarla?:** Identificable por enunciados que preguntan por el momento en que cesa el experimento o frases clave como: "calcular la probabilidad de que se tenga que evaluar a 10 niños para encontrar al primero que contraiga la enfermedad".


### 6. Propiedades de la Distribución Geométrica (Parámetros)

$$\text{Media (Esperanza): } \mu = E(X) = \frac{1}{p}$$

$$\text{Varianza: } \sigma^2 = V(X) = \frac{q}{p^2} = \frac{1-p}{p^2}$$

$$\text{Desviación Típica: } \sigma = \sqrt{\frac{1-p}{p^2}}$$

- **¿Cuándo utilizarla?:** Para determinar cuántos ensayos en promedio se deben ejecutar antes de observar el primer éxito bajo condiciones de Bernoulli.


---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Ajuste estricto de Lambda ($\lambda$) en Poisson:** El error más grave y recurrente en los exámenes de Poisson es utilizar el valor de $\lambda$ tal como viene en el texto sin adecuarlo al intervalo de la pregunta. Si el enunciado dice que ocurre un promedio de 4 accidentes por semana, y la pregunta pide la probabilidad de eventos en un periodo de dos semanas, debes ajustar obligatoriamente el parámetro por proporcionalidad lineal directa ($\lambda = 4 \times 2 = 8$).
    
- **Resolución Eficiente por Complemento:** Cuando los problemas pidan calcular probabilidades acumuladas del tipo "al menos 1" ($P(X \ge 1)$) o "como mínimo 2", evita realizar sumas extensas. Utiliza la regla del complemento respaldada por los textos institucionales:
    
    $$P(X \ge 1) = 1 - P(X < 1) = 1 - P(X = 0)$$
    
- **Definición del Éxito según la Pregunta:** El concepto de "Éxito" en probabilidad discreta es estrictamente operativo y no social; representa el evento que se está contando. Si un problema describe la probabilidad de que un artículo sea _defectuoso_, el conteo de artículos defectuosos se define matemáticamente como el "éxito" ($p$), y los artículos buenos corresponden al "fracaso" ($q$).
    
- **Límites Inferiores en la Distribución Geométrica:** Recuerda que para el modelo geométrico, el valor mínimo absoluto que puede tomar la variable es $x = 1$ (ya que se requiere al menos un ensayo para observar un éxito). Un valor de $x = 0$ no tiene sentido matemático ni físico en esta distribución.
    
- **Uso correcto de Factoriales:** En las calculadoras, asegúrate de colocar correctamente los paréntesis al computar denominadores combinatorios o de Poisson para evitar que la división afecte solo al primer término (ej. en Poisson escribe $\frac{e^{-λ} * λ^x}{(x!)}$).


---
## Paso a Paso de Resolución (Algoritmo para Ejercicios de Distribuciones Discretas)

Para enfrentarte con éxito a cualquier problema práctico de esta unidad en una evaluación escrita, aplica de forma secuencial los siguientes pasos lógicos:

1. **Identificar el Modelo de Distribución:** Analiza minuciosamente las condiciones estructurales del enunciado:
    
    - Si hay un número fijo de ensayos finitos independientes con dos opciones posibles $\rightarrow$ **Binomial**.
        
    - Si los eventos ocurren de forma libre en un intervalo continuo de tiempo o espacio a partir de un promedio $\rightarrow$ **Poisson**.
        
    - Si el experimento se repite de manera sucesiva hasta lograr el primer resultado favorable $\rightarrow$ **Geométrica**.
    
2. **Extraer e Identificar los Parámetros del Problema:**
    
    - Para Binomial: Define explícitamente el tamaño de muestra $n$ y la probabilidad de éxito $p$. Calcula $q = 1 - p$.
        
    - Para Poisson: Extrae el promedio original y compáralo con el intervalo de la pregunta. Si los intervalos difieren, realiza la regla de tres simple para establecer el $\lambda$ corregido.
        
    - Para Geométrica: Identifica la probabilidad fija de éxito $p$.
    
3. **Traducir la Pregunta a Notación Algebraica:** Expresa con precisión el evento solicitado usando operadores de desigualdad o igualdad según las frases del texto (ej. "como máximo 3" se traduce en $P(X \le 3)$; "más de 2" se traduce en $P(X > 2)$).
    
4. **Desglosar las Probabilidades Puntuales Necesarias:**
    
    - Si es una igualdad directa ($P(X = 4)$), selecciona la fórmula del modelo y sustituye los parámetros de forma directa.
        
    - Si es una desigualdad, desglosa la operación en la suma de sus componentes enteros discretos correspondientes (ej. $P(X \le 2) = P(X=0) + P(X=1) + P(X=2)$) o aplica el complemento conveniente si el camino es más corto.
        
5. **Efectuar el Cálculo Numérico y Verificar Coherencia:** Realiza las operaciones matemáticas de forma pausada en la calculadora. Evalúa con criterio pedagógico el resultado final: debe ser estrictamente un valor numérico real comprendido en el intervalo cerrado de $[0, 1]$.

---
## Síntesis de Retención (Puntos Clave)

- **Binomial:** Cuenta los éxitos obtenidos dentro de un número cerrado y constante de $n$ ensayos independientes de Bernoulli.
    
- **Poisson:** Modela frecuencias o conteos de eventos raros independientes que se manifiestan a lo largo de un continuo de espacio o tiempo bajo un parámetro constante $\lambda$.
    
- **Geométrica:** Mide el esfuerzo o la cantidad de ensayos requeridos hasta que se presenta por primera vez el éxito buscado.
    
- **Parámetros:** La media de la distribución binomial depende de la cantidad de pruebas ($\mu = np$), mientras que en Poisson la tasa promedio coincide numéricamente con el valor de su varianza ($\mu = \sigma^2 = \lambda$).