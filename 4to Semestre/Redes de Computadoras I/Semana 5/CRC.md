Para saber qué tipos de errores puede detectar un **CRC (Cyclic Redundancy Check)**, no necesitas hacer divisiones largas; solo necesitas observar las propiedades matemáticas de su **polinomio generador $G(x)$**.
- [I] **CRC:** técnica para identificar errores y garantiza que un paquete llegue a su destino exactamente igual a como fue enviado, sin que se haya alterado ningún bit en el camino.
- [*] **CRC - Cyclic Redundancy Check:** comprobación de redunddancia cíclica.
### 1. Detección de errores de un solo bit (Single-bit errors)

Esta es la capacidad más básica. Un CRC siempre detectará errores de un solo bit si el polinomio generador $G(x)$ cumple con una condición simple:
- **La regla:** El polinomio debe tener al menos **dos términos**, y el término de menor grado debe ser **1** ($x^0$).    
- **Por qué:** Un error de un solo bit se representa como $E(x) = x^i$. Para que el error no sea detectado, $G(x)$ tendría que dividir exactamente a $x^i$, lo cual es imposible si $G(x)$ tiene más de un término (como $x+1$ o $x^k + \dots + 1$).
### 2. Detección de una cantidad IMPAR de errores
Esta es una propiedad muy potente que no todos los polinomios tienen.
- **La regla:** El polinomio $G(x)$ debe ser **divisible por $(x + 1)$**.
- **Cómo saberlo rápido:** Suma los coeficientes del polinomio (o simplemente cuenta cuántos términos tiene). Si el número de términos es **par** (y termina en $+1$), entonces es divisible por $(x+1)$ y detectará **todos** los errores impares.
- **Ejemplo:** $G(x) = x^3 + x^2 + x + 1$ tiene 4 términos (par). Detectará cualquier error de 1, 3, 5, etc., bits.
### 3. Detección de una cantidad PAR de errores
Aquí es donde el CRC es más "vulnerable". **Ningún CRC puede garantizar la detección del 100% de los errores pares.**
- **La regla:** La capacidad depende de la **distancia mínima** del código, pero físicamente lo vemos por la longitud de la ráfaga (burst).
- **Lo que sí garantiza:** Un polinomio de grado $L$ (donde el término mayor es $x^L$) detectará:
    - Todos los errores de ráfaga (bits seguidos, sean pares o impares) de longitud menor o igual a **$L$**.
    - Por ejemplo, si tu polinomio es de grado 16 (CRC-16), cualquier error par que ocurra dentro de un bloque de 16 bits seguidos será detectado.
- **Si los errores están muy dispersos:** Existe una probabilidad de $1/2^L$ de que un error par pase desapercibido (se "escape").
---
## Resumen de comprobación rápida

Si te dan un polinomio $G(x)$, verifica esto en orden:

|**Tipo de Error**|**Requisito del Polinomio**|
|---|---|
|**1 solo bit**|Que tenga más de un término y termine en $+1$.|
|**Cualquier cantidad impar**|Que tenga a $(x+1)$ como factor (normalmente tiene un número par de términos).|
|**Ráfagas (pares o impares)**|Se detectan todas si la longitud de la ráfaga $\le$ grado del polinomio.|
|**Dos bits aislados**|Que $G(x)$ no divida a $(x^k + 1)$ para ningún $k$ menor a la longitud del mensaje.|

**Dato curioso:** La mayoría de los estándares industriales (como el CRC-32 de Ethernet) están diseñados específicamente para incluir el factor $(x+1)$, asegurando así que nunca se les pase un error impar, por complejo que sea.