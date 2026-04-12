# Varianza

La varianza es una medida estadística que nos dice **qué tan dispersos o alejados están los datos respecto a su promedio (la media)**.

Dependiendo de cómo tengas organizados tus datos, la fórmula cambia un poco. Aquí tienes la explicación directa para ambos casos, divididos siempre en si estás analizando una **población** (todos los elementos que existen de lo que estudias) o una **muestra** (solo una parte representativa).

---
## 1. Varianza para Datos Simples (No agrupados)

Se usa cuando tienes una lista sencilla y directa de números (por ejemplo, las edades de 5 amigos: 18, 20, 19, 21, 18).

### A. Si es una Población ($\sigma^2$):

Se divide entre el número exacto de datos ($N$).

$$\sigma^2 = \frac{\sum (x_i - \mu)^2}{N}$$

### B. Si es una Muestra ($s^2$):

Se divide entre $n-1$ (esto se conoce como "corrección de Bessel" y sirve para que la estimación sea más precisa cuando no tenemos todos los datos).

$$s^2 = \frac{\sum (x_i - \bar{x})^2}{n-1}$$

>[!note] ¿Qué significa cada letra?
>- $x_i$: Cada uno de los valores individuales de tu lista.
>- $\mu$ (o $\bar{x}$): El promedio (la media) de tus datos.
>- $N$ (o $n$): La cantidad total de datos que tienes.
>- $\sum$: Significa que debes sumar el resultado de todos esos cálculos individuales.

---
## 2. Varianza para Datos Discretos

Los datos discretos suelen presentarse de dos formas: agrupados en una **tabla de frecuencias** (cuando un mismo dato se repite varias veces) o como una **distribución de probabilidad** (como en los ejercicios que acabamos de resolver).

### Caso A: Tabla de Frecuencias

Se usa cuando tienes datos repetidos y los agrupas. Por ejemplo: 10 familias tienen 1 hijo, 5 familias tienen 2 hijos, etc.

**Poblacional:**

$$\sigma^2 = \frac{\sum f_i \cdot (x_i - \mu)^2}{N}$$

**Muestral:**

$$s^2 = \frac{\sum f_i \cdot (x_i - \bar{x})^2}{n-1}$$

- $f_i$: Es la **frecuencia absoluta**, es decir, cuántas veces se repite ese dato exacto. El resto de las variables significan lo mismo que en los datos simples.

### Caso B: Distribución de Probabilidad

Se usa cuando, en lugar de frecuencias, tienes la probabilidad de que ocurra cada evento (como en tu problema de las bombillas o los componentes electrónicos).

$$\sigma^2 = \sum [(x_i - \mu)^2 \cdot P(x_i)]$$

También existe una fórmula abreviada muy popular usando la Esperanza Matemática $E(X)$:

$$\sigma^2 = E(X^2) - [E(X)]^2$$

- $P(x_i)$: Es la probabilidad de que ocurra el dato $x_i$.
    
- $\mu$: En este caso, la media es el "Valor Esperado" o Esperanza Matemática.

---
