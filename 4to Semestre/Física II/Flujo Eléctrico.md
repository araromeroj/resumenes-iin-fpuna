El **flujo eléctrico** es una medida de la cantidad de campo eléctrico que atraviesa una superficie determinada. Es un concepto escalar que ayuda a visualizar la "fuerza" del campo a través de un área.

## 1. Definición Conceptual

Se puede imaginar como el número de líneas de campo eléctrico que pasan por una superficie.

- Si la superficie es **perpendicular** al campo, el flujo es máximo.
- Si la superficie es **paralela** al campo, el flujo es cero (las líneas no la "atraviesan").

## 2. Fórmulas Matemáticas

### Campo Eléctrico Uniforme

Para una superficie plana de área $A$:

$$\Phi_E = E \cdot A \cdot \cos(\theta)$$

Donde:

- **$\Phi_E$**: Flujo eléctrico ($N \cdot m^2 / C$).    
- **$E$**: Magnitud del campo eléctrico.
- **$A$**: Área de la superficie.
- **$\theta$**: Ángulo entre el vector de campo eléctrico y el **vector normal** a la superficie (el vector perpendicular a la cara).

### Definición General (Integral)

Para superficies irregulares o campos no uniformes:
$$\Phi_E = \int \vec{E} \cdot d\vec{A}$$

## 3. Flujo en Superficies Cerradas

Cuando tratamos con un volumen (como una esfera o un cubo), el flujo neto depende de las cargas que hay en su interior:

- **Flujo Positivo ($>0$):** Las líneas salen de la superficie (hay una carga neta positiva dentro).
    
- **Flujo Negativo ($<0$):** Las líneas entran a la superficie (hay una carga neta negativa dentro).
    
- **Flujo Nulo ($=0$):** El número de líneas que entran es igual al que salen, o no hay carga encerrada.

---

## 4. Ley de Gauss

Es la herramienta más potente para calcular flujos en superficies cerradas. Establece que el flujo neto a través de cualquier superficie cerrada es proporcional a la carga neta encerrada.

$$\Phi_E = \frac{Q_{enc}}{\epsilon_0}$$

Donde:

- **$Q_{enc}$**: Carga total dentro de la superficie.
- **$\epsilon_0$**: Permitividad del vacío ($8.85 \cdot 10^{-12} \, C^2 / N \cdot m^2$).

---

**Vínculos relacionados:**

- [[1. Electricidad]]
- [[Campo Eléctrico]]
- [[Ley de Gauss]]