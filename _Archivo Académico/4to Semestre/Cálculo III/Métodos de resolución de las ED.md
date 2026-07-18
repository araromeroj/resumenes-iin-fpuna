
|**Tipo de ED**|**¿Cómo la identificas a simple vista?**|**El "Truco" (Método o Sustitución)**|**En qué se transforma**|
|---|---|---|---|
|**Separable**|Se pueden agrupar todas las $x$ y las $y$ separadas por el $=$|Multiplicar/Dividir algebraicamente|Solución directa al integrar|
|**Lineal**|$y' + P(x)y = f(x)$ (la $y$ y la $y'$ no tienen exponentes)|Multiplicar por factor integrante $\mu(x) = e^{\int P(x) dx}$|Derivada de un producto|
|**Exacta**|$M dx + N dy = 0$ y además $\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$|Integrar $M$ respecto a $x$, derivar, comparar con $N$|Se halla la función original $f(x,y)=C$|
|**Homogénea**|$M dx + N dy = 0$ y todos los términos tienen el **mismo grado**|Sustituir $y = ux$ y $dy = u dx + x du$|Se vuelve **Separable**|
|**Bernoulli**|$y' + P(x)y = f(x)y^n$ (hay una $y^n$ arruinando la linealidad)|Dividir entre $y^n$ y sustituir $u = y^{1-n}$|Se vuelve **Lineal**|
|**$f(Ax+By+C)$**|$y' = f(Ax+By+C)$ (las variables están atrapadas en una función)|Sustituir el interior $u = Ax + By + C$|Se vuelve **Separable**|

---

## ¿Qué pasa si NO es ninguna de las anteriores?

Este es el verdadero terror de los exámenes. Si pasaste tu ecuación por todos los filtros de la tabla superior y no encaja en ninguno, estás frente a los **"Casos Especiales"**.

Aquí tienes las 4 salidas de emergencia:

**1. Ecuaciones que se pueden "forzar" a ser Exactas**

Si tiene la forma $M dx + N dy = 0$ pero falló la prueba de exactitud ($\frac{\partial M}{\partial y} \neq \frac{\partial N}{\partial x}$), debes buscar un **Factor Integrante especial**. Se intenta calcular una función que dependa solo de $x$ o solo de $y$. Al multiplicar toda la ecuación por ese factor, mágicamente se vuelve exacta.

**2. La Ecuación de Riccati**

Se parece mucho a Bernoulli, pero es ligeramente más malvada. Tiene la forma:

$$y' = P(x) + Q(x)y + R(x)y^2$$

El problema es ese término $P(x)$ suelto que impide usar el método de Bernoulli. Para resolverla, el problema **debe** darte (o debes adivinar) una solución particular conocida $y_1$. Si la tienes, aplicas la sustitución $y = y_1 + \frac{1}{u}$ y la ecuación colapsará en una Lineal.

**3. La Ecuación de Clairaut**

Tiene una estructura muy peculiar y fácil de reconocer si sabes qué buscar:

$$y = xy' + f(y')$$

Su solución es curiosamente simple. La solución general se obtiene cambiando todas las derivadas $y'$ por una constante $C$: $y = Cx + f(C)$ (una familia de líneas rectas). Luego se deriva respecto a $C$ para buscar una solución "singular" o curva envolvente.

**4. Sustituciones a la Medida (Por Inspección)**

A veces, el álgebra de la ecuación te "grita" una sustitución geométrica.

- **Ejemplo:** Si ves muchos términos repetidos como $x^2 + y^2$ y agrupaciones de $x dx + y dy$, la ecuación te está pidiendo a gritos un cambio a **coordenadas polares**: $x = r \cos \theta$ y $y = r \operatorname{sen} \theta$.
    

> **Nota de la vida real:** Si agotas todas estas opciones y la ecuación sigue sin ceder, entras al terreno de los **Métodos Numéricos**. En ingeniería y física, muchísimas ecuaciones diferenciales no tienen una solución matemática perfecta (analítica). En esos casos, usamos algoritmos de computadora (como Euler o Runge-Kutta) para dibujar aproximaciones súper precisas de la solución sin resolverla algebraicamente.
