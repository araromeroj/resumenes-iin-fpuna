#EnlaceDeDatos
El **CRC (Cálculo de Redundancia Cíclica)** es un método de detección de errores basado en el tratamiento de los mensajes y las palabras codificadas como **polinomios** con coeficientes binarios (0 o 1). Es una de las técnicas de control de errores más utilizadas en la [[2. Capa de Enlace de Datos|capa de enlace de datos]] para asegurar que las tramas se reciban íntegras tras pasar por medios físicos ruidosos.

## ¿Qué es el CRC y cómo detecta errores?

El algoritmo se basa en la aritmética de **módulo 2** y utiliza un **polinomio generador $G(x)$** predefinido y conocido tanto por el emisor como por el receptor. La efectividad del CRC depende del diseño de este polinomio:

- **Detección de ráfagas:** Un polinomio de grado $r$ garantiza la detección de cualquier ráfaga de errores cuya longitud $L$ sea menor o igual a $r$ ($L \le r$) si $G(x)$ contiene un término $x^0$.
- **Errores de un solo bit:** Se detectan siempre que el polinomio tenga al menos dos términos.
- **Errores impares:** Si $G(x)$ incluye el factor $(x + 1)$, podrá detectar todos los errores que afecten a un número impar de bits.

## Método para aplicar el CRC en la transmisión

El proceso se divide en los pasos realizados por el emisor y el receptor:

### En el Emisor:

1. **Anexar bits:** Se determina el grado $r$ del polinomio generador $G(x)$ y se añaden $r$ bits "0" al final del mensaje original $m(x)$.
2. **División:** Se divide el mensaje resultante ($m(x) \cdot x^r$) entre $G(x)$ utilizando aritmética de módulo 2 (XOR).
3. **Obtener el código:** El resto de esta división (que tendrá $r$ o menos bits) se resta al mensaje con los ceros. En la práctica, esto equivale a **reemplazar los ceros añadidos por el resto obtenido**, generando la trama final $T(x)$, la cual es perfectamente divisible por $G(x)$.

### En el Receptor:

1. **Nueva división:** Al recibir la trama, el receptor la divide nuevamente por el mismo polinomio generador $G(x)$.
2. **Verificación:**
    - Si el **resto es 0**, se asume que la trama llegó sin errores.
    - Si el resto es distinto de 0, significa que ocurrió un error de transmisión y la trama se rechaza.

**Dato estratégico:** El código CRC se coloca normalmente en el **tráiler** (al final del mensaje) porque esto permite que el hardware calcule el valor **mientras los bits van saliendo** por la interfaz, optimizando la velocidad del proceso.

## Errores de transmisión

![[Pasted image 20260420160339.png|400]]

$$E(x) = x^i$$
donde:
- $i$ es la ubicación del bit con error (contado de derecha a izquierda).

>[!important] Entonces:
>Si $G(x)$ tiene más de un término, $E(x)/G(x)$ nunca será exacto y detectará todos los errores de un bit.

![[Pasted image 20260420160720.png|400]]
### Errores de cantidad impar de bits

>[!important] Propiedades
>Un generador $G(x)$ que contiene a un factor igual a $(x+1)$ puede detectar todos los errores **impares**.
>Si la división de $G(x)\% (x+1) \neq 0$
>$(x+1)$ no divide a ningún polinomio con número impar de términos.
>Si al realizar la división de G(x) entre (x+1) el resto es cero, todos los errores con número impar de bits serán detectados.


### Errores de ráfaga

>[!important] Propiedades
>Todas las ráfagas de error con $L\leq r$ serán detectados si $G(x)$ contiene un término $x^0$
>El término independiente de $G(x)$ debe tener el valor de "1" a fin de mejorar la detección de ráfagas de error.

## Análisis del polinomio generador


![[Pasted image 20260420161749.png]]

## Práctica hecha en clase

![[IMG_20260420_162010.jpg|400]]

---
# Resumen

Para garantizar que un sistema de **Redundancia Cíclica (CRC)** sea efectivo, el **polinomio generador $G(x)$** de grado $r$ debe diseñarse con propiedades matemáticas específicas según el tipo de error que se desee detectar:

- **Errores de 1 solo bit:**
    - Para detectar todos los errores de un bit, el polinomio $G(x)$ debe tener **al menos dos términos** distintos de cero. Esto asegura que el polinomio de error $E(x) = x^i$ nunca sea divisible exactamente por $G(x)$.
    
- **Errores en cantidad impar de bits:**
    - El polinomio $G(x)$ debe contener el **factor $(x + 1)$**. Dado que $(x + 1)$ no divide a ningún polinomio que tenga un número impar de términos, incluirlo como factor permite detectar cualquier error que afecte a una cantidad impar de bits.
    
- **Errores de 2 bits (dobles aislados):**
    - Para detectar todos los errores dobles, $G(x)$ **no debe dividir al polinomio $x^t + 1$** para todos los valores de $t$ entre 1 y $n-1$ (donde $n$ es la longitud total de la trama). Si la división es inexacta para cualquier distancia $t$ entre los bits erróneos, el error será detectado.
    
- **Errores de ráfaga (Burst errors):**
    - Un polinomio de grado $r$ detecta siempre todas las ráfagas de longitud **$L \le r$**.
    - Además, el **término independiente ($x^0$)** del polinomio debe ser igual a **1** para mejorar la capacidad de detección de este tipo de errores.
    
- **Errores en cantidad par:**
    - No existe una propiedad única simplificada para detectar _toda_ cantidad par de bits erróneos más allá de las reglas generales de divisibilidad. Sin embargo, al cumplir con las propiedades para detectar errores de 2 bits y poseer un grado $r$ elevado (como en el estándar CRC-32), la probabilidad de que un error par sea un múltiplo exacto de $G(x)$ y pase desapercibido es extremadamente baja.

### Resumen de propiedades de $G(x)$

| **Tipo de Error**      | **Propiedad requerida en $G(x)$**               |
| :--------------------- | :---------------------------------------------- |
| **1 bit**              | Al menos dos términos.                          |
| **Cantidad impar**     | Debe tener $(x + 1)$ como factor.               |
| **2 bits**             | No debe dividir a $x^t + 1$ para $1 < t < n-1$. |
| **Ráfaga ($L \le r$)** | El término independiente $x^0$ debe ser 1.      |