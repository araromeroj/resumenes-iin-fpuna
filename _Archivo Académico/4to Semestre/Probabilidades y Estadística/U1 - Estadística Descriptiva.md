Este concepto e información estructurada pertenecen de forma exclusiva a la **Unidad 1: Estadística Descriptiva**.
## Teoría Detallada

La Estadística Descriptiva es la rama de la estadística que se encarga de la recolección, organización, resumen y presentación de datos muestrales correspondientes a variables. Su propósito es hacer comprensible el comportamiento de un conjunto de datos a través de tablas, gráficos y medidas numéricas.

### 1. Conceptos Fundamentales

- **Población:** Es la colección completa de todos los elementos o individuos que se van a estudiar.
    
- **Muestra:** Es una parte o subconjunto representativo seleccionado de la población para realizar el estudio correspondiente.
    
- **Estadístico (o estadístico muestral):** Es una medida o un valor numérico que se calcula para describir una característica a partir de los datos de una sola muestra.
    
- **Variable Estadística:** Es una característica o cualidad de un individuo o elemento de la población que está propensa a adquirir diferentes valores y que se caracteriza por poder medirse o contarse.

### 2. Clasificación de Variables

De acuerdo con sus características, las variables se dividen estrictamente en dos tipos principales, los cuales determinan los métodos de tabulación y análisis que se aplicarán:

- **Variable Cualitativa (o categórica):** Expresa únicamente un atributo o característica no numérica. Se subdivide en:
    
    - **Nominal:** Los valores no siguen ningún orden ni jerarquía específica (ej. colores de autos, estado civil).
        
    - **Ordinal:** Los valores siguen un orden, secuencia o jerarquía establecida (ej. nivel socioeconómico alto, medio o bajo).
        
- **Variable Cuantitativa:** Se expresa en forma numérica y representa un conteo o medición directa. Se subdivide en:
    
    - **Discreta:** Resulta cuando el número de valores posibles es finito o contable (ej. cantidad de hijos por familia).
        
    - **Continua:** Resulta cuando existe un número infinito de valores posibles dentro de un rango determinado debido a una escala de medición continua (ej. estaturas, temperaturas).

### 3. Distribución de Frecuencias y Tabulación

Una distribución de frecuencias es una ordenación en forma de tabla de los datos muestrales, que asigna a cada valor (o grupo de valores) sus frecuencias correspondientes para entender la naturaleza de su distribución. Las columnas esenciales de una tabla completa son:

- **Frecuencia Absoluta ($f_i$):** Número de veces que se repite o se observa un determinado valor de la variable en la muestra. La sumatoria de todas las frecuencias absolutas es igual al tamaño total de la muestra ($n$).
    
- **Frecuencia Relativa ($f_{ri}$):** Es el cociente entre la frecuencia absoluta de un valor y el tamaño de la muestra ($f_{ri} = f_i / n$). Indica la proporción de datos que pertenecen a esa categoría, y su sumatoria total debe ser igual a 1.
    
- **Frecuencia Porcentual ($f_p$):** Indica el porcentaje del total de elementos que corresponde a esa clase ($f_p = f_{ri} \times 100\%$).
    
- **Frecuencia Absoluta Acumulada ($f_{iac}$ o $F_i$):** Es la suma de las frecuencias absolutas de todos los valores inferiores o iguales al valor considerado. Puede ser ascendente o descendente según los requerimientos de análisis gráficos como las ojivas.
    
- **Frecuencia Relativa Acumulada ($f_{rac}$):** Es la suma de las frecuencias relativas de todos los valores inferiores o iguales al valor considerado.

### 4. Tabulación por Intervalos (Datos Agrupados)

Cuando se maneja una variable continua o una variable discreta con un gran número de valores distintos, es necesario agrupar los datos en intervalos de clase.

- **Intervalo de Clase:** Símbolo que define una categoría delimitada por dos extremos. El menor es el Límite Inferior ($L_i$) y el mayor es el Límite Superior ($L_s$).
    
- **Marca de Clase ($x_i$):** Es el punto medio de un intervalo de clase, calculado como el promedio entre sus límites. Actúa como el valor representativo del intervalo para el cálculo de medidas numéricas.
    
- **Anchura o Amplitud de Clase ($C$):** Es la distancia entre los límites de un intervalo de clase.

### 5. Representaciones Gráficas

- **Diagrama Lineal o Gráfico de Líneas:** Utilizado para mostrar tendencias de variables a lo largo del tiempo.
    
- **Diagrama de Barras:** Representación gráfica en coordenadas cartesianas donde la altura es proporcional a la frecuencia. Puede presentarse en modalidades como barras compuestas para comparar subcategorías.
    
- **Gráfico de Sectores (Circular):** Muestra la proporción porcentual de cada categoría respecto al total.
    
- **Histograma:** Gráfico de barras continuas (unidas) para datos agrupados en intervalos. Las bases de los rectángulos corresponden a la amplitud del intervalo y sus alturas a las frecuencias absolutas.
    
- **Polígono de Frecuencias:** Gráfico de líneas que une los puntos medios (marcas de clase) superiores de las barras de un histograma.
    
- **Ojivas:** Gráficos de líneas continuas para frecuencias acumuladas. La ojiva "menor que" empieza en cero y asciende progresivamente; la ojiva "mayor que" empieza en el total de los datos y desciende progresivamente.

### 6. Medidas Estadísticas Numéricas

- **Medidas de Tendencia Central:** Valores numéricos que se localizan en el centro o en la mitad de un conjunto de datos, sirviendo como representantes globales de la muestra. Incluyen la Media (promedio aritmético), la Mediana (punto central que divide los datos al 50%) y la Moda (el valor con mayor frecuencia absoluta). Un conjunto de datos con dos modas se denomina bimodal.
    
- **Medidas de Dispersión:** Valores numéricos que describen la variabilidad o el grado de alejamiento de los datos con respecto a la media central. Permiten complementar la descripción de los datos determinando si estos se concentran cerca del centro o están muy dispersos. Incluyen la Varianza (promedio del cuadrado de las distancias a la media) y la Desviación Estándar (raíz cuadrada de la varianza).

---
## Guía de Fórmulas y Aplicación

### 1. Número de Intervalos de Clase (Fórmula de Sturges)

$$K = 1 + 3.322(\log_{10} n)$$

- **Significado de variables:**
    
    - $K$: Número sugerido de intervalos o clases (se suele redondear a un valor entero conveniente).
        
    - $n$: Tamaño de la muestra o cantidad total de frecuencias de los datos bajo estudio.
        
    - $\log_{10}$: Logaritmo en base 10.
        
- **¿Cuándo utilizarla?:** Se aplica al inicio de la construcción de una tabla de frecuencias para variables continuas o discretas con un gran volumen de datos distintos, cuando el enunciado te pide agrupar los datos o estructurarlos en intervalos de clase.    

### 2. Anchura o Amplitud de Clase

$$C = \frac{R}{K}$$

- **Significado de variables:**
    
    - $C$: Anchura, tamaño o amplitud de cada intervalo de clase.
        
    - $R$: Rango de los datos, calculado como el dato máximo menos el dato mínimo ($R = \text{Dato Máx} - \text{Dato Mín}$).
        
    - $K$: Número de clases calculado previamente por Sturges o criterio asignado.
        
- **¿Cuándo utilizarla?:** Inmediatamente después de determinar el número de clases $K$, para establecer la distancia que tendrá cada intervalo al construir los límites de la tabla.    

### 3. Marca de Clase

$$x_i = \frac{L_i + L_s}{2}$$

- **Significado de variables:**
    
    - $x_i$: Marca de clase u operando central del intervalo de la fila $i$.
        
    - $L_i$: Límite inferior del intervalo de clase correspondiente.
        
    - $L_s$: Límite superior del intervalo de clase correspondiente.
        
- **¿Cuándo utilizarla?:** Se calcula para rellenar la columna de marcas de clase en tablas de datos agrupados, y es indispensable como paso previo para calcular la media, la varianza y la desviación estándar de datos agrupados.

### 4. Media Aritmética para Datos No Agrupados

$$\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}$$

- **Significado de variables:**
    
    - $\bar{x}$: Media muestral (promedio aritmético).
        
    - $x_i$: Valor de cada observación o dato individual de la muestra.
        
    - $n$: Tamaño total de la muestra.
        
- **¿Cuándo utilizarla?:** Cuando el enunciado solicita calcular el "promedio" o "media" de un listado simple de datos sueltos de tamaño pequeño que no han sido estructurados en intervalos.

### 5. Media Aritmética para Datos Agrupados en Clases

$$\bar{x} = \frac{\sum_{i=1}^{K} x_i \cdot f_i}{n}$$

- **Significado de variables:**
    
    - $\bar{x}$: Media muestral de datos agrupados.
        
    - $x_i$: Marca de clase de cada intervalo $i$.
        
    - $f_i$: Frecuencia absoluta de cada intervalo $i$.
        
    - $n$: Tamaño total de la muestra ($\sum f_i$).
        
- **¿Cuándo utilizarla?:** Cuando los datos se presentan tabulados dentro de una tabla de intervalos de clase y el problema requiere encontrar el valor medio o promedio representativo.

### 6. Mediana para Datos Agrupados (Variables Continuas)

$$Me = LRI + \left( \frac{\frac{n}{2} - \sum f_{ant}}{f_{ma}} \right) \cdot C$$

- **Significado de variables:**
    
    - $Me$: Valor de la mediana calculada.
        
    - $LRI$: Límite real inferior (o límite inferior formal) del intervalo de clase que contiene a la mediana.
        
    - $n$: Cantidad total de frecuencias o tamaño de la muestra.
        
    - $\sum f_{ant}$: Frecuencia absoluta acumulada del intervalo inmediatamente anterior al intervalo de la mediana.
        
    - $f_{ma}$: Frecuencia absoluta propia del intervalo de clase que contiene a la mediana.
        
    - $C$: Tamaño, ancho o amplitud del intervalo de clase que contiene a la mediana.
        
- **¿Cuándo utilizarla?:** Cuando los datos corresponden a una variable continua agrupada en intervalos y el enunciado pide calcular la "mediana" o el valor que divide al 50% de la muestra.  

### 7. Moda para Datos Agrupados (Variables Continuas)

$$Mo = L_i + \left( \frac{\Delta_1}{\Delta_1 + \Delta_2} \right) \cdot C$$

- **Significado de variables:**
    
    - $Mo$: Valor de la moda calculada.
        
    - $L_i$ (o $LRI$): Límite inferior del intervalo de clase modal (el intervalo con la frecuencia absoluta $f_i$ más alta).
        
    - $\Delta_1$: Diferencia entre la frecuencia absoluta del intervalo modal y la frecuencia absoluta del intervalo inmediato anterior ($\Delta_1 = f_{\text{modal}} - f_{\text{anterior}}$).
        
    - $\Delta_2$: Diferencia entre la frecuencia absoluta del intervalo modal y la frecuencia absoluta del intervalo inmediato siguiente ($\Delta_2 = f_{\text{modal}} - f_{\text{siguiente}}$).
        
    - $C$: Tamaño o ancho del intervalo de clase modal.
        
- **¿Cuándo utilizarla?:** Cuando el problema presenta datos agrupados en intervalos de clase y pide hallar la "moda" o el valor que se presenta con mayor frecuencia o repetición.

### 8. Varianza Muestral para Datos No Agrupados

$$s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n - 1}$$

- **Significado de variables:**
    
    - $s^2$: Varianza muestral.
        
    - $x_i$: Valor de cada observación individual de la muestra.
        
    - $\bar{x}$: Media aritmética de los datos muestrales.
        
    - $n$: Tamaño total de la muestra.
        
- **¿Cuándo utilizarla?:** Cuando el enunciado pide explícitamente calcular la "varianza" o medir la variabilidad de un conjunto pequeño de observaciones independientes no agrupadas en intervalos.

### 9. Desviación Estándar o Típica Muestral

$$s = \sqrt{s^2}$$

- **Significado de variables:**
    
    - $s$: Desviación estándar o típica de la muestra.
        
    - $s^2$: Varianza muestral calculada previamente.
        
- **¿Cuándo utilizarla?:** Siempre que el ejercicio solicite la "desviación típica" o "desviación estándar", sirviendo como la métrica de dispersión expresada en las mismas unidades originales de la variable.

---
## Detalles Clave y Errores Comunes (Checklist para examen)

- **Denotación de Parámetros vs. Estadísticos:** Asegúrate de leer bien si los datos corresponden a una muestra o a una población completa. La varianza muestral se denota como $s^2$ y utiliza denominador $n-1$, mientras que la poblacional se denota por $\sigma^2$ y usa denominador $N$.
    
- **Redondeo en Sturges y Amplitud ($C$):** Al aplicar Sturges para obtener $K$, si da un número decimal (ej. $6.32$), se evalúa redondear a un número entero conveniente (ej. $6$). Al calcular la anchura $C$, generalmente se redondea hacia arriba para asegurar que todos los datos queden contenidos dentro de los intervalos construídos.
    
- **Uso estricto de la Marca de Clase:** Al calcular la media o varianza de datos agrupados, un error común es multiplicar la frecuencia absoluta ($f_i$) por los límites del intervalo. Recuerda que se debe multiplicar estrictamente por la marca de clase ($x_i$).
    
- **Identificación del intervalo de la Mediana:** Antes de aplicar la fórmula de la mediana en datos agrupados, primero se debe calcular la posición $\frac{n}{2}$. Luego, busca este valor posicional fijándote en la columna de frecuencias absolutas acumuladas ($f_{iac}$); el primer intervalo acumulado que iguale o supere a $\frac{n}{2}$ será el intervalo seleccionado para extraer los componentes de la fórmula.
    
- **Cálculo correcto de deltas ($\Delta_1$ y $\Delta_2$) en la Moda:** Verifica que al calcular las diferencias de frecuencias no arrastres signos negativos. $\Delta_1$ y $\Delta_2$ siempre deben ser valores positivos porque restas la frecuencia del intervalo modal (que es la máxima) menos las frecuencias vecinas.
    
- **Unidades de Medida:** La varianza arroja resultados expresados en unidades al cuadrado (ej. $cm^2$, $^{\circ}C^2$), mientras que la media, la mediana, la moda y la desviación estándar conservan exactamente la misma unidad de medida lineal que los datos originales.    

## Paso a Paso de Resolución (Algoritmo para Ejercicios de Tabulación y Medidas)

Para resolver de manera estructurada un ejercicio completo donde te entregan una lista de datos numéricos continuos o discretos y te solicitan construir la tabla y calcular sus medidas estadísticas, sigue los siguientes pasos lógicos:

1. **Ordenar y Contar:** Ordena los datos de menor a mayor para facilitar el conteo visual de frecuencias. Cuenta el número total de datos para establecer el valor de $n$. Identifica el dato mínimo y el dato máximo.
    
2. **Definir la Estructura de Intervalos:**
    
    - Calcula el Rango: $R = \text{Dato Máx} - \text{Dato Mín}$.
        
    - Determina el número de clases $K$ aplicando la fórmula de Sturges ($K = 1 + 3.322 \log n$) y redondea convenientemente.
        
    - Determina la amplitud del intervalo: $C = R / K$.
    
3. **Construir los Intervalos de Clase:** Comienza fijando el límite inferior de la primera clase ($L_i$) igual al dato más bajo o un valor ligeramente menor conveniente. Suma la amplitud $C$ para fijar el límite superior ($L_s$) e inferiores sucesivos, construyendo consecutivamente todas las clases hasta cubrir el rango completo.
    
4. **Calcular Marcas de Clase e Identificar Frecuencias:**
    
    - Para cada fila de intervalo, calcula su punto medio o marca de clase: $x_i = (L_i + L_s) / 2$.
        
    - Haz el recuento físico de cuántos datos caen dentro de cada intervalo para rellenar la columna de frecuencia absoluta ($f_i$).
        
    - Completa las columnas adicionales requeridas: frecuencia relativa ($f_{ri}$), porcentual ($f_p$) y frecuencias acumuladas ($f_{iac}$).
    
5. **Calcular Medidas de Tendencia Central:**
    
    - **Media:** Añade una columna con el producto $x_i \cdot f_i$. Suma todos los resultados de esa columna y divídelos entre $n$.
        
    - **Mediana:** Ubica la posición calculando $n/2$. Localiza el intervalo correspondiente en la columna de frecuencias acumuladas y aplica la fórmula de interpolación de la mediana.
        
    - **Moda:** Encuentra el intervalo con la frecuencia absoluta $f_i$ más alta. Calcula las diferencias $\Delta_1$ y $\Delta_2$, y aplica la fórmula de la moda.
    
6. **Calcular Medidas de Dispersión:** Aplica el procedimiento de desvíos elevados al cuadrado multiplicados por la frecuencia absoluta para determinar la varianza muestral, y finalmente extrae su raíz cuadrada para reportar la desviación estándar.

---
## Síntesis de Retención (Puntos Clave)

- **Variables:** Las cualitativas expresan categorías o atributos ; las cuantitativas representan cantidades contables (discretas) o medibles sobre escalas continuas (continuas).
    
- **Tabulación:** Agrupar en intervalos es mandatorio para simplificar grandes colecciones de datos cuantitativos mediante el uso coordinado de las fórmulas de Sturges y rango.
    
- **Marcas de Clase:** Representan matemáticamente a los intervalos y son indispensables para calcular promedios y variabilidad en datos agrupados.
    
- **Centro vs. Dispersión:** Las medidas centrales (media, mediana, moda) indican el punto de equilibrio o representativo del grupo de datos , mientras que las medidas de dispersión (varianza, desviación estándar) miden qué tan dispersos o concentrados se encuentran los datos respecto a ese centro.