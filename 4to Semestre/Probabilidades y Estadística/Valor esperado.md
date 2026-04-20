El **valor esperado** (también conocido como Esperanza Matemática o media teórica, y denotado como $E(X)$ o $\mu$) representa el promedio a largo plazo que obtendrías si repitieras un experimento infinitas veces.

Para encontrar el valor esperado, existe una fórmula general matemática:

- **Para variables discretas:** Multiplicas cada valor posible por su probabilidad y sumas todo: $E(X) = \sum x \cdot P(X=x)$
- **Para variables continuas:** Usas integrales en lugar de sumatorias: $E(X) = \int x \cdot f(x) dx$
---
## 1. Para Variables Discretas

### Distribución Binomial

Es simplemente el total de intentos multiplicado por la probabilidad de que uno sea exitoso.

$$E(X) = n \cdot p$$

- _Ejemplo:_ Si tiras 100 monedas ($n=100$) y la probabilidad de cara es 0.5 ($p=0.5$), esperas obtener $100 \cdot 0.5 = 50$ caras.


### Distribución de Poisson

Esta es la más fácil de todas, porque el parámetro $\lambda$ que define la distribución ya es, por definición, el promedio o valor esperado.

$$E(X) = \lambda$$

### Distribución Geométrica

Si $X$ es el número total de intentos hasta conseguir el **primer** éxito.

$$E(X) = \frac{1}{p}$$

- _Ejemplo:_ Si la probabilidad de sacar un 6 en un dado es $1/6$, en promedio tendrás que tirar el dado $1 / (1/6) = 6$ veces para conseguirlo.


### Distribución Binomial Negativa (o de Pascal)

Si $X$ es el número total de intentos hasta conseguir **$k$** éxitos. (Es literalmente $k$ veces el valor esperado de la geométrica).

$$E(X) = \frac{k}{p}$$

### Distribución Hipergeométrica

Es el tamaño de tu muestra multiplicado por la proporción de "éxitos" que hay en la población total.

$$E(X) = n \cdot \left(\frac{K}{N}\right)$$

---

## 2. Para Variables Continuas

### Distribución Normal (de Gauss)

Al igual que en Poisson, el parámetro central de la distribución ($\mu$) ya es directamente el valor esperado. Físicamente es el punto más alto y central de la campana.

$$E(X) = \mu$$

### Distribución Exponencial

Es el inverso de la tasa de ocurrencia ($\lambda$) de los eventos.

$$E(X) = \frac{1}{\lambda}$$

- _Ejemplo:_ Si llegan en promedio 4 clientes por hora ($\lambda = 4$ en Poisson), el tiempo esperado que transcurre _entre_ un cliente y el siguiente es $1/4$ de hora (15 minutos).


### Distribución Uniforme Continua

Como la probabilidad es un rectángulo perfectamente plano, el valor esperado siempre será exactamente la mitad del camino entre el mínimo y el máximo (el promedio aritmético simple de los extremos).

$$E(X) = \frac{a+b}{2}$$---
