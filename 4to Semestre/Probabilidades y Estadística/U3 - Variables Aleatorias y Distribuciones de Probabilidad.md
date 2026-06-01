Este concepto e información estructurada pertenecen de forma exclusiva a la **Unidad 3: Variables Aleatorias y Distribuciones de Probabilidad**.

## Síntesis Teórica Detallada

Esta unidad establece el puente definitivo entre la teoría de la probabilidad pura (estudiada en la unidad anterior) y el análisis inferencial, mediante la formalización matemática de los resultados de un experimento aleatorio en forma de variables numéricas.

### 1. Concepto de Variable Aleatoria (v.a.)

- Una **Variable Aleatoria** es una función que asigna un valor numérico real a cada resultado posible de un espacio muestral correspondiente a un experimento aleatorio.
    
- Matemáticamente, actúa tomando elementos del espacio muestral ($S$) y transformándolos en puntos sobre la recta real ($\mathbb{R}$).
    
- Se denota tradicionalmente con letras mayúsculas (por ejemplo, $X$, $Y$ o $Z$), mientras que los valores numéricos específicos que puede asumir se escriben con letras minúsculas correspondientes ($x_1, x_2, \dots$).    

### 2. Clasificación de Variables Aleatorias

De acuerdo con la naturaleza del conjunto de valores que pueden asumir, las variables aleatorias se clasifican estrictamente en:

- **Variable Aleatoria Discreta:** Es aquella que puede tomar un conjunto de valores finito o infinito numerable (contable). Generalmente se asocia a procesos de conteo, como el número de artículos defectuosos en un lote o la cantidad de llamadas que recibe una central.
    
- **Variable Aleatoria Continua:** Es aquella que puede tomar cualquier valor real dentro de un intervalo o un conjunto de intervalos continuos. Se asocia a procesos de medición física, tales como el tiempo, el peso, el volumen, la temperatura o la longitud.    

### 3. Distribuciones de Probabilidad para Variables Discretas

- **Función de Probabilidad (o función de masa de probabilidad, $P(X = x_i)$ o $f(x_i)$):** Es una función que asigna a cada valor específico $x_i$ de la variable aleatoria discreta su probabilidad exacta de ocurrencia. Para que una función sea considerada una distribución de probabilidad válida, debe cumplir estrictamente dos propiedades fundamentales:
    
    1. No negatividad: $f(x_i) \ge 0$ para todo valor $x_i$.
        
    2. Condición de cierre o normalización: La sumatoria de las probabilidades de todos los valores posibles de la variable debe ser exactamente igual a la unidad ($\sum f(x_i) = 1$).
    
- **Función de Distribución Acumulada ($F(x)$):** Especifica la probabilidad de que la variable aleatoria $X$ tome un valor menor o igual a un punto dado $x$. Matemáticamente se expresa como $F(x) = P(X \le x) = \sum_{x_i \le x} f(x_i)$. Es una función monótona no decreciente que escala desde 0 hasta 1.

### 4. Distribuciones de Probabilidad para Variables Continuas

- **Función de Densidad de Probabilidad ($f(x)$):** A diferencia de las variables discretas, una variable aleatoria continua no puede asignar una probabilidad puntual distinta de cero a un valor exacto (es decir, $P(X = x) = 0$ para cualquier valor individual $x$). Por lo tanto, la distribución se describe mediante una curva continua de densidad. Las probabilidades se representan exclusivamente como áreas bajo dicha curva matemática. Debe cumplir con:
    
    1. $f(x) \ge 0$ para todo $x$.
        
    2. El área total bajo la curva completa sobre el eje real es igual a 1 ($\int_{-\infty}^{\infty} f(x) dx = 1$).
    
- **Probabilidad como Área:** La probabilidad de que una variable continua tome valores dentro de un intervalo comprendido entre $a$ y $b$ equivale analíticamente al área bajo la función de densidad entre esos dos puntos limitantes. Debido a que la probabilidad en un punto exacto es nula, se cumple estrictamente que:  $$P(a \le X \le b) = P(a < X \le b) = P(a \le X < b) = P(a < X < b)$$

### 5. Valores Característicos (Parámetros) de una Variable Aleatoria

- **Valor Esperado, Esperanza Matemática o Media ($\mu$ o $E(X)$):** Representa el valor promedio teórico a largo plazo que se obtendría si el experimento aleatorio se repitiera un número infinito de veces bajo condiciones idénticas. Actúa como el centro de gravedad o medida de centralización de la distribución de probabilidad.
    
- **Varianza ($\sigma^2$ o $V(X)$):** Es una medida del grado de dispersión o variabilidad de los valores de la variable aleatoria con respecto a su valor esperado o media. Mide el promedio ponderado de las desviaciones cuadráticas.
    
- **Desviación Estándar ($\sigma$):** Es la raíz cuadrada positiva de la varianza. Tiene la ventaja pedagógica de expresarse en las mismas unidades lineales que la variable original $X$.

---
## Guía de Fórmulas y Aplicación

### 1. Valor Esperado (Esperanza Matemática) para Variables Discretas

$$\mu = E(X) = \sum_{i=1}^{k} x_i \cdot P(X = x_i)$$

- **Significado de variables:**
    
    - $\mu$ o $E(X)$: Esperanza matemática o media teórica de la variable.
        
    - $x_i$: Cada uno de los valores numéricos individuales que puede asumir la v.a.
        
    - $P(X = x_i)$ o $f(x_i)$: Probabilidad exacta asignada al valor $x_i$.
    
- **¿Cuándo utilizarla?:** En enunciados de variables discretas donde se solicita hallar el "valor esperado", el "número esperado", el "promedio a largo plazo" o la "esperanza" de un fenómeno tabulado o con funciones de masa conocidas (ej. "Calcular el número esperado de preguntas formuladas en años anteriores").    

### 2. Varianza de una Variable Aleatoria Discreta (Fórmula Conceptual)

$$\sigma^2 = V(X) = \sum_{i=1}^{k} (x_i - \mu)^2 \cdot P(X = x_i)$$

- **Significado de variables:**
    
    - $\sigma^2$ o $V(X)$: Varianza de la distribución de probabilidad.
        
    - $\mu$: Valor esperado calculado previamente.
        
    - $(x_i - \mu)^2$: Desviación cuadrática de cada valor respecto a la media.
    
- **¿Cuándo utilizarla?:** Cuando se requiere determinar cuantitativamente la dispersión de una variable aleatoria discreta a partir de su definición formal.


### 3. Varianza de una Variable Aleatoria Discreta (Fórmula de Trabajo Operativa)

$$\sigma^2 = E(X^2) - [E(X)]^2 = \left( \sum_{i=1}^{k} x_i^2 \cdot P(X = x_i) \right) - \mu^2$$

- **Significado de variables:**
    
    - $E(X^2)$: Segundo momento teórico o esperanza de la variable elevada al cuadrado.
        
    - $\mu^2$: El cuadrado de la esperanza matemática obtenida en el primer paso.
    
- **¿Cuándo utilizarla?:** Es la fórmula analítica preferida para agilizar los cálculos en exámenes, reduciendo los errores de redondeo asociados al restar decimales en cada fila.

### 4. Desviación Estándar de una Variable Aleatoria

$$\sigma = \sqrt{\sigma^2}$$

- **Significado de variables:**
    
    - $\sigma$: Desviación estándar o típica de la v.a.
        
    - $\sigma^2$: Varianza calculada previamente.
    
- **¿Cuándo utilizarla?:** Siempre que el ejercicio pida explícitamente reportar la "desviación estándar", sirviendo como el indicador final de la dispersión en las unidades físicas reales del problema

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Verificación de la Condición de Cierre:** Ante cualquier problema de tabla de distribución discreta, lo primero que debes comprobar es si $\sum P(X = x_i) = 1$. Si falta una probabilidad (denotada comúnmente con la letra $k$ o $c$), despéjala restando a 1 la suma de las probabilidades conocidas.
    
- **El Teorema del Valor Puntual Continuo:** Recuerda bajo estricta prioridad que para cualquier función de densidad continua, $P(X = c) = 0$. Si el enunciado de un examen te pide calcular la probabilidad de que el tiempo de reparación sea _exactamente_ de 3 horas para una variable continua, la respuesta matemática es automáticamente 0. Por ende, los símbolos $<$ y $\le$ son equivalentes en cálculos continuos.
    
- **Confusión entre $E(X^2)$ y $[E(X)]^2$:** Es el error algebraico más recurrente en los exámenes de esta unidad.
    
    - Para $E(X^2)$, primero debes elevar cada valor $x_i$ al cuadrado y luego multiplicarlo por su respectiva probabilidad.
        
    - Para $[E(X)]^2$, tomas el resultado final de la media $\mu$ y lo elevas por completo al cuadrado al final de la operación.
    
- **Signo de la Varianza:** Debido a que es una suma de desvíos al cuadrado multiplicados por probabilidades no negativas, la varianza **jamás puede ser negativa**. Si en tus cálculos obtienes un valor negativo, revisa de inmediato el paso de la resta operativa, ya que probablemente restaste los términos en el orden inverso o cometiste un error de signos.
    
- **Interpretación del Valor Esperado:** El valor esperado no tiene que ser necesariamente uno de los valores físicos que la variable puede asumir. Por ejemplo, el número esperado de preguntas puede resultar en $1.7$ (como se observa en los materiales adjuntos), aun cuando físicamente solo se puedan formular cantidades enteras como 1 o 2 preguntas.

---
## Paso a Paso de Resolución (Algoritmo para Problemas de Distribuciones Discretas)

Si te enfrentas a un problema clásico de la Unidad 3 que involucre el análisis de una variable aleatoria discreta a partir de un experimento combinatorio o una tabla provista, sigue metódicamente esta secuencia de pasos lógicos:

1. **Definir la Variable Aleatoria:** Redacta con precisión qué magnitud numérica representa la variable (ej. $X$: Número de preguntas formuladas en años anteriores al extraer tres al azar).
    
2. **Determinar el Rango Matemático ($x_i$):** Identifica minuciosamente todos los valores enteros posibles que puede tomar la variable $X$. Comienza típicamente desde 0 hasta el límite físico impuesto por el experimento (ej. $x_i = \{0, 1, 2, 3\}$).
    
3. **Calcular el Espacio de Probabilidades:** Aplica las reglas de combinatoria o probabilidad analítica para hallar la probabilidad exacta de cada escenario posible. Construye una tabla organizada con dos columnas principales: los valores $x_i$ y sus probabilidades $P(X = x_i)$.
    
4. **Control de Calidad Analítico:** Suma todas las probabilidades obtenidas en la tabla. Verifica estrictamente que el resultado sea igual a $1.00$. Si no cierra, revisa los cálculos combinatorios del paso anterior.
    
5. **Calcular la Medida Central (Esperanza):** Construye una tercera columna en tu tabla calculando el producto $x_i \cdot P(X = x_i)$ para cada fila. Suma por completo los componentes de esta columna para obtener de forma directa el Valor Esperado $\mu = E(X)$.
    
6. **Calcular la Medida de Dispersión (Varianza y Desviación):** * Construye una cuarta columna calculando los elementos $x_i^2 \cdot P(X = x_i)$. Suma la columna entera para obtener el valor general de $E(X^2)$.
    
    - Aplica la fórmula operativa restando la media al cuadrado: $\sigma^2 = E(X^2) - \mu^2$.
        
    - Extrae la raíz cuadrada del resultado para obtener la desviación estándar lineal ($\sigma$).

---
## Síntesis de Retención (Puntos Clave)

- **Variable Aleatoria:** Transformación matemática que convierte los resultados abstractos de un espacio muestral en valores numéricos reales cuantificables.
    
- **Discreta vs. Continua:** Las discretas asignan probabilidades directas a puntos aislados (sumatorias); las continuas asignan probabilidades únicamente a intervalos mediante áreas (integrales bajo la curva de densidad).
    
- **Propiedades obligatorias:** Las probabilidades individuales jamás son negativas y su acumulación o suma total sobre todo el espacio de estados debe dar rigurosamente 1.
    
- **Esperanza y Varianza:** La esperanza matemática define el centro de equilibrio representativo de la distribución, mientras que la varianza establece cuantitativamente el nivel de dispersión interna de los datos aleatorios en torno a ese promedio.