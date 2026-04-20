# La Campana de Gauss y la Distribución Normal

Este método se basa en la **simetría** de la curva: el área total bajo la curva es 1 (el 100% de probabilidad), por lo que el área a la izquierda de la media es 0.5 y el área a la derecha de la media es 0.5.

Este enfoque asume que estás utilizando la **tabla de probabilidad normal estándar que te da el área desde la media (0) hasta un valor $Z$**. 

Antes de empezar, recuerda siempre el paso cero: estandarizar tu variable $X$ para convertirla en $Z$ usando la fórmula:

$$Z = \frac{X - \mu}{\sigma}$$

Donde $\mu$ es la media y $\sigma$ es la desviación estándar

$$\mu = n*p$$
$$\sigma = \sqrt{n*p*q}$$

---

### 1. Mayor que ($>$) o Mayor o igual que ($\ge$)

En las distribuciones continuas como la normal, un punto exacto no tiene área. Por lo tanto, **$P(Z > z)$ es exactamente lo mismo que $P(Z \ge z)$**. No te dejes engañar por el "o igual", se calculan igual.

- **Si $Z$ es positivo (buscas la cola derecha):**
    
    El valor de la tabla te da el área desde el centro hasta tu $Z$. Como la mitad derecha completa vale 0.5, debes **restar**.
    
    **Fórmula:** $P(Z > z) = 0.5 - (\text{Valor de la tabla para } z)$
    
    _Ejemplo visual:_ Si $Z = 1.5$, la tabla te da el área entre 0 y 1.5. Le restas eso a 0.5 para obtener la colita sobrante.
    
- **Si $Z$ es negativo (buscas casi toda la curva):**
    
    Estás a la izquierda del cero y quieres todo lo que está a la derecha. Eso incluye el pedazo desde tu $-Z$ hasta el centro, MÁS toda la mitad derecha completa que vale 0.5. Aquí debes **sumar**.
    
    **Fórmula:** $P(Z > -z) = 0.5 + (\text{Valor de la tabla para } z)$
    

### 2. Menor que ($<$) o Menor o igual que ($\le$)

Al igual que en el caso anterior, **$P(Z < z)$ es idéntico a $P(Z \le z)$**.

- **Si $Z$ es positivo (buscas casi toda la curva):**
    
    Estás a la derecha del centro y quieres todo lo que está a tu izquierda. Eso incluye el pedazo desde el centro hasta tu $Z$, MÁS toda la mitad izquierda completa. Debes **sumar**.
    
    **Fórmula:** $P(Z < z) = 0.5 + (\text{Valor de la tabla para } z)$
    
- **Si $Z$ es negativo (buscas la cola izquierda):**
    
    Por simetría, la cola izquierda es igual a la cola derecha. Simplemente busca el valor positivo en la tabla y **resta** de 0.5.
    
    **Fórmula:** $P(Z < -z) = 0.5 - (\text{Valor de la tabla para } z)$
    

### 3. Entre incluyente ($\le X \le$) o Entre excluyente ($< X <$)

Nuevamente, los símbolos de inclusión/exclusión no cambian el resultado. Aquí importan los signos de tus dos valores $Z$.

- **Si ambos $Z$ tienen el MISMO signo (ambos positivos o ambos negativos):**
    
    Están del mismo lado de la campana. Buscas el área grande desde el centro y le recortas el área pequeña que no necesitas. Aquí debes **restar** las probabilidades de la tabla.
    
    **Fórmula:** $(\text{Valor de tabla del } Z \text{ mayor}) - (\text{Valor de tabla del } Z \text{ menor})$
    
- **Si los $Z$ tienen SIGNOS OPUESTOS (uno negativo y uno positivo):**
    
    El área que buscas cruza el centro (el cero). Tienes un pedazo a la izquierda y un pedazo a la derecha. Aquí debes **sumar** ambas áreas.
    
    **Fórmula:** $(\text{Valor de tabla del } Z \text{ negativo}) + (\text{Valor de tabla del } Z \text{ positivo})$
    

### 4. Igual a ($=$)

Esta es una pregunta trampa clásica de los profesores de estadística.

- **La regla de oro:** En cualquier distribución continua, la probabilidad de que una variable tome un valor _exacto_ y puntual es cero.
    
- **Respuesta automática:** $P(X = x) = 0$.
    
- _¿Por qué?_ Porque el área de una línea sin grosor bajo la curva es cero.
    

### 5. Fronteras o Probabilidad Inversa (Te dan el % y piden $X$)

Este es el proceso inverso. Tienes el área y necesitas encontrar $Z$ para luego despejar $X$ con la fórmula estandarizada: $X = Z \sigma + \mu$.

**Tips para resolver fronteras con el método 0.5 y 0.5:**

1. **Dibuja la campana:** Esto es no negociable. Ubica si el área que te dan está a la izquierda o a la derecha.    
2. **Ajusta el área para la tabla:** Recuerda, tu tabla _solo lee áreas desde el centro (0) hasta $Z$_.
    - Si te dicen "el 10% superior" (cola derecha), tu tabla no tiene 0.10. El área desde el centro hasta esa frontera es $0.5 - 0.10 = 0.40$. Buscas 0.4000 _dentro_ de la tabla.
    - Si te dicen "el 80% inferior", eso cruza el centro (abarca el 0.5 izquierdo entero y entra 0.30 en el lado derecho). Buscas 0.3000 _dentro_ de la tabla.
3. **Lee el valor de $Z$ en los márgenes:** Una vez que encuentras el área más cercana adentro de la tabla, miras hacia los bordes para armar tu $Z$ (ej. fila 1.2, columna 0.08 = $Z$ de 1.28).
4. **Asigna el signo lógico:** ¡La tabla nunca te dará un signo negativo! Si tu dibujo muestra que la frontera está a la izquierda del centro, **tú** debes ponerle el signo negativo a tu $Z$ antes de despejar $X$.


>[!summary] Regla de oro general:
>Si el área o probabilidad que te piden es **mayor al 50% (0.5)**, en algún punto vas a tener que **sumar 0.5** a tu valor de tabla (porque cruza la mitad de la campana). Si el área es **menor al 50%**, vas a tener que **restar de 0.5** o solo usar el área recortada. Siempre dibuja la curva y pinta el área que buscas, tu cerebro sabrá inmediatamente si tienes que sumar o restar.