## 1. Distribuciones para Variables Discretas (Conteo)

Estas fórmulas calculan la **Función de Masa de Probabilidad (FMP)**, que es la probabilidad exacta de que la variable tome un valor específico, denotada como $P(X=x)$.

### Distribución Binomial

Calcula el número de éxitos en una cantidad fija de ensayos independientes.

$$P(X=x) = \binom{n}{x} \cdot p^x \cdot (q)^{n-x}$$

- $n$: Número total de ensayos.    
- $x$: Número de éxitos deseados.    
- $p$: Probabilidad de éxito en cada ensayo.    
- $q=(1-p)$: Probabilidad de fracaso.
- El paréntesis es Combinatoria de $n$ elementos tomados de a $x$.

### Distribución de Poisson

Calcula el número de eventos en un intervalo fijo de tiempo o espacio.

$$P(X=x) = \frac{e^{-\lambda} \cdot \lambda^x}{x!}$$

- $x$: Número de ocurrencias del evento.    
- $\lambda$: Tasa promedio de ocurrencia (media).    
- $e$: Base del logaritmo natural (aproximadamente **2.71828**).    

### Distribución Geométrica

Calcula el número del ensayo en el que ocurre el **primer** éxito.

$$P(X=x) = (1-p)^{x-1} \cdot p$$

- $x$: Número del ensayo donde ocurre el primer éxito.  
- $p$: Probabilidad de éxito en cada ensayo.

### Distribución Binomial Negativa (o de Pascal)

Calcula el número total de ensayos necesarios para lograr un número específico de éxitos.

$$P(X=n) = \binom{n-1}{k-1} \cdot p^k \cdot (1-p)^{n-k}$$

- $n$: Número total de ensayos hasta obtener el éxito deseado.
- $k$: Número del éxito deseado (ej. el 2do éxito, 3er éxito).
- $p$: Probabilidad de éxito en cada ensayo.
- El paréntesis indica combinatoria de $(n-1)$ elementos tomados de a $(k-1)$.

### Distribución Hipergeométrica

Calcula éxitos en una muestra extraída de una población **sin reemplazo**.

$$P(X=x) = \frac{\binom{K}{x} \cdot \binom{N-K}{n-x}}{\binom{N}{n}}$$

- $N$: Tamaño total de la población.
- $K$: Cantidad total de "éxitos" disponibles en la población.
- $n$: Tamaño de la muestra extraída.    
- $x$: Número de éxitos observados en la muestra.

---

## 2. Distribuciones para Variables Continuas (Medición)

Estas fórmulas representan la **Función de Densidad de Probabilidad (FDP)**, denotada como $f(x)$. En variables continuas, la probabilidad de un valor exacto siempre es cero; la probabilidad se calcula encontrando el área bajo la curva de esta función (usando integrales) en un intervalo específico.

### Distribución Normal (de Gauss)

La distribución clásica en forma de campana, simétrica respecto a su centro.

$$f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$$

- $x$: Valor de la variable continua.    
- $\mu$: Media de la distribución.    
- $\sigma$: Desviación estándar.  
- $\pi$: Constante Pi (aproximadamente **3.14159**).

---
>[!note] Segundo Parcial
### Distribución Exponencial

Modela el tiempo o espacio que transcurre entre eventos en un proceso de Poisson.

$$f(x) = \lambda e^{-\lambda x} \quad \text{para } x \ge 0$$

- $x$: Tiempo o distancia transcurrida.    
- $\lambda$: Tasa de ocurrencia (la misma $\lambda$ de Poisson).    

### Distribución Uniforme Continua

Modela variables donde todos los subintervalos de la misma longitud tienen la misma probabilidad (forma rectangular).

$$f(x) = \frac{1}{b-a} \quad \text{para } a \le x \le b$$

- $x$: Valor de la variable continua dentro del intervalo.
- $a$: Límite inferior del intervalo.
- $b$: Límite superior del intervalo.

---
