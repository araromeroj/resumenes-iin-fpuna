Este concepto e información estructurada pertenecen de forma exclusiva a la **Unidad 8: Pruebas de Hipótesis** (basado estrictamente en los materiales de lectura institucionales y metodologías de la Universidad Nacional de Asunción suministrados).

### Síntesis Teórica Detallada

La inferencia estadística también engloba la toma de decisiones relativas a una población sobre la base de las informaciones obtenidas de una muestra aleatoria. La **Prueba de Hipótesis** es un procedimiento regulado por reglas lógicas que determina si se acepta o se rechaza una afirmación matemática sobre un parámetro poblacional.

### 1. Formulación de Hipótesis Mutuamente Excluyentes

- **Hipótesis Nula ($H_0$):** Es la hipótesis afirmada o supuesta que se somete a prueba estadísticamente. Representa el estado de no cambio, efecto nulo o igualdad matemática (siempre contiene los signos $=$, $\le$ o $\ge$). Se asume como verdadera de entrada hasta que los datos de la muestra demuestren lo contrario.
    
- **Hipótesis Alternativa ($H_1$):** Es la declaración contraria que se acepta únicamente si se logra aportar suficiente evidencia empírica para rechazar la hipótesis nula. Contiene los signos de desigualdad estricta ($\neq$, $<$ o $>$), y establece la dirección o tipo de prueba a realizar.

### 2. Tipos de Pruebas según la Dirección del Rechazo

La dirección de la prueba está condicionada de manera exclusiva por el símbolo lógico de la Hipótesis Alternativa ($H_1$):

- **Prueba Bilateral o de Dos Colas:** Se configura cuando la hipótesis alternativa utiliza el signo de desigualdad "diferente de" ($\neq$). La zona de rechazo se divide de forma simétrica en los dos extremos de la distribución de probabilidad (con un área de $\alpha/2$ a cada lado).
    
- **Prueba Unilateral de Cola Izquierda:** Se activa cuando en $H_1$ aparece el signo "menor que" ($<$), concentrando toda la región de rechazo de forma única en el extremo inferior izquierdo de la curva.
    
- **Prueba Unilateral de Cola Derecha:** Ocurre cuando en $H_1$ se declara el signo "mayor que" ($>$), situando la zona de rechazo por completo en el extremo superior de la distribución.

### 3. Los Errores de Decisión en Muestreo

Debido al factor de aleatoriedad del muestreo, siempre existe el riesgo latente de cometer una conclusión errónea al tomar una decisión definitiva:

- **Error de Tipo I ($\alpha$):** Consiste en rechazar la Hipótesis Nula ($H_0$) cuando en realidad es verdadera en la población. La probabilidad máxima de cometer este error es el **Nivel de Significación ($\alpha$)**, fijado por el analista antes de la prueba.
    
- **Error de Tipo II ($\beta$):** Ocurre cuando no se rechaza la Hipótesis Nula ($H_0$) a pesar de que esta es falsa en la población. Su complemento ($1-\beta$) se denomina la _Potencia de la Prueba_.

### 4. Selección del Estadístico de Prueba según las Condiciones de la Población

- **Uso de la Distribución Normal ($Z$):** Se selecciona de manera estricta cuando el tamaño de la muestra es grande ($n \ge 30$) o cuando la desviación estándar de la población ($\sigma$) es un dato plenamente conocido por el investigador.
    
- **Uso de la Distribución t de Student ($t$):** Se debe aplicar obligatoriamente cuando el tamaño de la muestra es pequeño ($n < 30$) y la desviación estándar de la población ($\sigma$) es totalmente desconocida, teniendo que estimarse mediante la desviación estándar de la muestra ($s$).

---
## Guía de Fórmulas y Aplicación

### 1. Estadístico de Prueba para una Media Poblacional ($\mu$) - Desviación Poblacional Conocida o Muestra Grande

$$Z_{\text{calc}} = \frac{\bar{x} - \mu_0}{\frac{\sigma}{\sqrt{n}}}$$

- **Significado de variables:**
    
    - $Z_{\text{calc}}$: Estadístico de prueba estandarizado (adimensional, se redondea a 2 decimales para su comparación en tablas).
        
    - $\bar{x}$: Media aritmética observada de los datos de la muestra.
        
    - $\mu_0$: Valor numérico hipotético del parámetro declarado bajo la hipótesis nula ($H_0$).
        
    - $\sigma$: Desviación estándar poblacional conocida. (Si es desconocida pero $n \ge 30$, se sustituye por $s$).
        
    - $n$: Número total de observaciones de la muestra.
    
- **¿Cuándo utilizarla?:** En enunciados donde se evalúa si el promedio real de un proceso ha cambiado, aumentado o disminuido, con muestras grandes ($n \ge 30$) o conociendo el valor histórico de $\sigma$.

### 2. Estadístico de Prueba para una Proporción Poblacional ($p$)

$$Z_{\text{calc}} = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0 \cdot q_0}{n}}}$$

- **Significado de variables:**
    
    - $\hat{p}$: Proporción de éxitos calculada en la muestra observada ($\hat{p} = x/n$).
        
    - $p_0$: Proporción poblacional supuesta bajo la condición fija de la hipótesis nula ($H_0$).
        
    - $q_0$: Fracción de fracasos esperada bajo la validez de $H_0$ ($q_0 = 1 - p_0$).
        
- **¿Cuándo utilizarla?:** En problemas vinculados a tasas, fracciones o porcentajes (ej. "evaluar si la proporción de piezas con fallas supera el 5%"), bajo la condición de que $n \cdot p_0 \ge 5$ y $n \cdot q_0 \ge 5$.

### 3. Estadístico de Prueba para Diferencia de Medias Poblacionales ($\mu_1 - \mu_2$) - Grandes Muestras

$$Z_{\text{calc}} = \frac{(\bar{x}_1 - \bar{x}_2) - 0}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}}$$

- **Significado de variables:**
    
    - $\bar{x}_1, \bar{x}_2$: Promedios obtenidos de las muestras 1 y 2 de forma respectiva.
        
    - $\sigma_1^2, \sigma_2^2$: Varianzas de las poblaciones de origen. (Sustituidas por las varianzas muestrales $s_1^2, s_2^2$ ante muestras de tamaño grande) .
        
    - $n_1, n_2$: Tamaños de las muestras independientes seleccionadas para la prueba.
    
- **¿Cuándo utilizarla?:** Cuando el ejercicio te pida comprobar si existe una diferencia significativa entre el desempeño o rendimiento medio de dos grupos independientes.

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **El Signo de Igualdad Exclusivo de la Hipótesis Nula ($H_0$):** Jamás declares un signo de desigualdad estricta ($<$, $>$, $\neq$) en $H_0$. Por normativa institucional y pedagógica, la hipótesis nula siempre lleva el signo de igualdad o inclusión ($=$, $\le$, $\ge$). La sospecha del investigador o la frase de cambio del enunciado siempre va directo a $H_1$.
    
- **Determinación de Signos en el Estadístico de Prueba ($Z_{\text{calc}}$):** No alteres el orden del numerador de la fórmula. Es estrictamente $\bar{x} - \mu_0$. Si el promedio muestral es inferior al supuesto poblacional, el estadístico de prueba saldrá con signo negativo obligatoriamente. Conservar el signo real es indispensable para validar si cae o no en la región de rechazo de cola izquierda.
    
- **Error Estándar de Proporciones con Parámetro Teórico:** Al calcular el error estándar (denominador) en la prueba de proporciones, es un error fatal usar los valores muestrales $\hat{p}$ y $\hat{q}$ bajo la raíz. A diferencia de los intervalos de confianza de la Unidad 7, en las pruebas de hipótesis debes utilizar estrictamente los valores teóricos de la hipótesis nula, es decir, $p_0$ y $q_0$.
    
- **Cálculo Previo de Estadísticos si el Enunciado entrega los Datos Crudos:** Tal como recalcan los apuntes de la cátedra, si el examen te presenta listas o bases de datos sin procesar en lugar de los promedios directos, tu primer paso técnico obligatorio antes de iniciar la prueba de hipótesis es calcular manualmente $\bar{x}$ y la desviación estándar $s$ mediante las fórmulas básicas de estadística descriptiva.

---
## Paso a Paso de Resolución (Algoritmo para Pruebas de Hipótesis)

Sigue de forma rigurosa y ordenada este procedimiento de pasos lógicos institucionales para resolver cualquier ejercicio de examen de esta sección:

1. **Paso 1: Plantear las Hipótesis de la Prueba ($H_0$ y $H_1$):** Lee con cuidado el enunciado, identifica el parámetro de interés y traduce las afirmaciones a lenguaje matemático formal. Determina si la prueba es unilateral (una cola) o bilateral (dos colas) de acuerdo al símbolo lógico de $H_1$.
    
2. **Paso 2: Fijar el Nivel de Significación ($\alpha$) y Seleccionar la Distribución:** Registra la probabilidad máxima tolerable de Error Tipo I establecida por el enunciado (ej. $\alpha = 0.05$ o $0.10$). Elige si trabajarás con la distribución Normal ($Z$) o t de Student ($t$) evaluando el tamaño muestral y el conocimiento de la desviación estándar poblacional.
    
3. **Paso 3: Definir la Región de Rechazo y Hallar el Valor Crítico ($Z_{\text{crítico}}$):** Acude a la tabla de probabilidad estadística correspondiente con los datos de $\alpha$:
    
    - Si es bilateral, busca el área dividida $\alpha/2$ para fijar los límites simétricos $\pm Z_{\text{crítico}}$.
        
    - Si es unilateral, busca el valor de área completo de $\alpha$ en la dirección indicada por $H_1$ para fijar el límite crítico (con su signo respectivo).
    
4. **Paso 4: Calcular el Valor del Estadístico de Prueba ($Z_{\text{calc}}$):** Introduce los estadísticos de la muestra en la fórmula seleccionada para hallar el valor estandarizado de comparación.
    
5. **Paso 5: Tomar la Decisión Estadística:** Compara el valor del estadístico calculado ($Z_{\text{calc}}$) con el valor crítico limitante ($Z_{\text{crítico}}$) establecido en la gráfica de tu paso 3:
    
    - Si $Z_{\text{calc}}$ cae dentro del rango delimitado como zona de rechazo, se procede a **Rechazar $H_0$**
        
    - Si cae en la zona central, se concluye que **No se rechaza $H_0$** (o se acepta provisionalmente por falta de evidencia en contra).
    
6. **Paso 6: Redactar la Conclusión Contextualizada:** Traduce la decisión matemática a una respuesta directa a la pregunta del problema (ej. _"A un nivel de significación del 5%, existe evidencia estadística suficiente para afirmar que el nuevo método pedagógico produce un promedio de rendimiento superior..."_ ).

---
## Síntesis de Retención (Puntos Clave)

- **El Objetivo Esencial:** Evaluar la veracidad de supuestos sobre parámetros de una población usando un estadístico muestral como elemento de prueba.
    
- **$H_0$ frente a $H_1$:** La hipótesis nula asume igualdad o condición de base ; la hipótesis alternativa recoge la sospecha de cambio y define los extremos de rechazo de la curva.
    
- **Nivel de Significación ($\alpha$):** Representa el área extrema de la distribución donde el resultado muestral se vuelve tan atípico que nos obliga a descartar la hipótesis nula como explicación plausible.
    
- **Decisión Final:** No se trata de una demostración absoluta, sino de un dictamen basado en la fuerza de la evidencia empírica que aporta la muestra.