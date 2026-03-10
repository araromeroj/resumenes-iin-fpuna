A diferencia de una solución explícita donde tenemos una función $y = \phi(x)$ totalmente despejada, una **solución implícita** es una relación matemática donde la variable dependiente $y$ está "mezclada" con la variable independiente $x$.

Para que una familia de relaciones sea considerada una solución implícita válida de una ecuación diferencial ordinaria (EDO), debe cumplir los siguientes criterios rigurosos:

---

## Presencia de la Constante (La Familia)

Para que estemos hablando de una _familia_ de soluciones (lo que suele ser la solución general), la relación matemática debe contener una constante arbitraria $C$ (o $n$ constantes si la EDO es de orden $n$). La forma típica de expresarlo es:

$$G(x, y) = C$$

Cada valor que le asignes a $C$ genera una gráfica diferente en el plano. A estas gráficas se les llama **curvas integrales**.

---

## Diferenciabilidad Implícita

La expresión $G(x, y) = C$ debe poder derivarse respecto a $x$. Como la $y$ no está despejada, el cálculo asume que $y$ depende de $x$ (es decir, $y = y(x)$) y exige el uso de la regla de la cadena de forma implícita. Las derivadas parciales de la relación deben existir en la región de interés.

---

## Reconstrucción de la EDO (Identidad)

El criterio definitivo es la prueba de fuego geométrica y algebraica: al derivar la relación $G(x, y) = C$ de manera implícita respecto a $x$, la nueva ecuación obtenida debe ser **exactamente igual** a la ecuación diferencial original, o bien, debes poder despejar $y'$ y sustituirlo en la EDO para obtener una identidad ($0 = 0$).

---

## Respaldo del Teorema de la Función Implícita

Para que la relación sea matemáticamente rigurosa, debe cumplir localmente con el **Teorema de la Función Implícita**. Esto garantiza que la "fórmula mezclada" realmente está ocultando una función válida.

En términos sencillos, dentro de un rectángulo en el plano $(x, y)$, la derivada parcial de la relación respecto a $y$ no debe ser nula:

$$\frac{\partial G}{\partial y} \neq 0$$

>[!important] Nota importante:
>Una relación implícita puede graficar figuras cerradas (como un círculo o una elipse) que por sí solas no son funciones, ya que fallan la prueba de la línea vertical. Sin embargo, el teorema asegura que al menos un "pedazo" de esa curva sí se comporta como una función válida $y(x)$ que resuelve la EDO.

---

### Comparación Rápida

|**Aspecto**|**Solución Explícita**|**Solución Implícita**|
|---|---|---|
|**Estructura**|$y = \phi(x)$|$G(x, y) = C$|
|**Variable dependiente**|Completamente aislada y despejada.|Combinada algebraicamente con $x$.|
|**Método de comprobación**|Derivación directa y sustitución.|Derivación implícita y comparación algrebraica.|
