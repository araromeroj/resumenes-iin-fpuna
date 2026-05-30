Este resumen ejecutivo presenta la teoría fundamental de la **Unidad 6: Distribuciones Muestrales**, estructurada para facilitar el estudio desde los fundamentos conceptuales hasta la aplicación de fórmulas específicas.

## 1. Fundamentos de la Inferencia Estadística

El propósito principal de la inferencia estadística es obtener conclusiones sobre **parámetros desconocidos** de una población mediante el estudio de **muestras aleatorias**. Debido a que estudiar una población completa suele ser costoso o lento, se recurre al muestreo.

**Conceptos clave:**

- **Población ($N$):** La totalidad de las observaciones de interés.
- **Muestra ($n$):** Un subconjunto seleccionado de la población.
- **Parámetro:** Una medida resumen (constante) de una característica poblacional, como la media ($\mu$), varianza ($\sigma^2$) o proporción ($P$).
- **Estadístico:** Una medida resumen calculada a partir de los datos de la muestra, como la media muestral ($\bar{x}$) o la proporción muestral ($p$). A diferencia del parámetro, el estadístico es una **variable aleatoria** que cambia de una muestra a otra.
- **Distribución Muestral:** Es la distribución de probabilidad de un estadístico. Describe cómo se comporta dicho estadístico al tomar muchas muestras aleatorias del mismo tamaño.

---

### 2. Distribución Muestral de Medias ($\bar{x}$)

Se utiliza para estudiar el comportamiento del promedio de una variable cuantitativa en una muestra.

**Propiedades:**

1. **Media:** La media de la distribución de medias es igual a la media poblacional: $\mu_{\bar{x}} = \mu$.
2. **Error Estándar ($\sigma_{\bar{x}}$):** Representa la variabilidad del estadístico.
    - **Población infinita o con reemplazo:** $\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}}$.
    - **Población finita ($N$) o sin reemplazo:** Se aplica el factor de corrección: $\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}} \cdot \sqrt{\frac{N-n}{N-1}}$.

**Estandarización (Fórmula para calcular probabilidades):** Si la muestra es grande ($n \geq 30$) o la población es normal, se utiliza la distribución normal estándar ($Z$): $$Z = \frac{\bar{x} - \mu}{\sigma_{\bar{x}}}$$.

---

### 3. Distribución Muestral de Diferencia de Medias ($\bar{x}_1 - \bar{x}_2$)

Se aplica al comparar los promedios de dos poblaciones independientes.

**Propiedades:**

1. **Media:** $\mu_{\bar{x}_1 - \bar{x}_2} = \mu_1 - \mu_2$.
2. **Error Estándar:** $\sigma_{\bar{x}_1 - \bar{x}_2} = \sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}$.

**Fórmula de estandarización ($Z$):** $$Z = \frac{(\bar{x}_1 - \bar{x}_2) - (\mu_1 - \mu_2)}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}}$$.

---

### 4. Distribución Muestral de la Proporción ($p$)

Se utiliza cuando la variable es **dicotómica** (ej: éxito/fracaso, sí/no) para estimar un porcentaje.

**Propiedades:**

1. **Media:** $\mu_p = P$ (la proporción poblacional).
2. **Error Estándar ($\sigma_p$):**
    - **Población infinita o con reemplazo:** $\sigma_p = \sqrt{\frac{P(1-P)}{n}}$.
    - **Población finita o sin reemplazo:** $\sigma_p = \sqrt{\frac{P(1-P)}{n}} \cdot \sqrt{\frac{N-n}{N-1}}$.

**Fórmula de estandarización ($Z$):** $$Z = \frac{p - P}{\sigma_p}$$.

---

### 5. Distribución Muestral de Diferencia de Proporciones ($p_1 - p_2$)

Permite comparar los porcentajes de una característica entre dos grupos independientes.

**Propiedades:**

1. **Media:** El valor esperado es la diferencia de las proporciones poblacionales: $P_1 - P_2$.
2. **Error Estándar:** $\sigma_{p_1 - p_2} = \sqrt{\frac{P_1(1-P_1)}{n_1} + \frac{P_2(1-P_2)}{n_2}}$.

**Fórmula de estandarización ($Z$):** $$Z = \frac{(p_1 - p_2) - (P_1 - P_2)}{\sqrt{\frac{P_1(1-P_1)}{n_1} + \frac{P_2(1-P_2)}{n_2}}}$$.

---

### 6. Guía Rápida para Decidir qué Distribución Usar

Para elegir la herramienta correcta, sigue estos criterios:

1. **Tipo de variable:**
    - ¿Es cuantitativa (números)? $\rightarrow$ Usa **Medias**.
    - ¿Es dicotómica (categorías)? $\rightarrow$ Usa **Proporciones**.
2. **Número de grupos:**
    - ¿Un solo grupo? $\rightarrow$ Media o Proporción simple.
    - ¿Comparación de dos grupos? $\rightarrow$ Diferencia de medias o de proporciones.
3. **Condiciones:** Verifica si la muestra es aleatoria, el tamaño de la misma ($n \geq 30$) o si la población sigue una distribución normal.

En resumen, no observamos a toda la población; tomamos una muestra, calculamos un estadístico y, a través de su **distribución muestral**, inferimos el valor real del parámetro poblacional con un margen de probabilidad conocido.