Para que una función sea "bien portada" en el cálculo, existen requisitos específicos que van escalando en exigencia.

>**toda función derivable es continua, pero no toda función continua es derivable.**

---
# Continuidad

Una función $f(x)$ es continua en un punto $a$ si no hay saltos, huecos o asíntotas en ese lugar.
## Condiciones

1. **Existencia de la imagen:** $f(a)$ debe estar definida.
2. **Existencia del límite:** El límite de la función cuando $x$ tiende a $a$ debe existir ($\lim_{x \to a} f(x) = L$). Esto implica que los límites laterales deben ser iguales:
$$\lim_{x \to a^-} f(x) = \lim_{x \to a^2} f(x)$$
3. **Coincidencia:** El valor del límite debe ser exactamente igual al valor de la imagen: $$\lim_{x \to a} f(x) = f(a)$$
---
# Derivabilidad (Diferenciabilidad)

Para que una función sea derivable en un punto $a$, primero **debe ser continua** en ese punto. Si es continua, entonces debe cumplir con lo siguiente:

- **Existencia del límite de la derivada:** El siguiente límite debe existir y ser un número real:    $$f'(a) = \lim_{h \to 0} \frac{f(a+h) - f(a)}{h}$$    
- **Suavidad (Derivadas laterales iguales):** Gráficamente, esto significa que no hay "picos" o esquinas. La pendiente por la izquierda debe ser igual a la pendiente por la derecha: $$f'_{-}(a) = f'_{+}(a)$$
>[!important] Nota importante
>La función valor absoluto $f(x) = |x|$ es el ejemplo clásico de una función que **es continua** en $x=0$ (puedes dibujarla sin levantar el lápiz), pero **no es derivable** en ese punto porque tiene un pico y sus derivadas laterales son diferentes ($-1$ y $1$).

---

# Resumen comparativo

| **Característica**   | **Continuidad**                              | **Derivabilidad**                                |
| -------------------- | -------------------------------------------- | ------------------------------------------------ |
| **Requisito visual** | No hay interrupciones o "huecos".            | La curva es "suave", sin esquinas.               |
| **Límites**          | Límites laterales de la función son iguales. | Límites laterales de la _pendiente_ son iguales. |
| **Relación**         | Es necesaria para la derivabilidad.          | Si existe, garantiza la continuidad.             |

# Enlaces Relacionados

 - [[1. Introducción- ED]]