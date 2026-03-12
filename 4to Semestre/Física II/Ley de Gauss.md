La **Ley de Gauss** establece que el flujo eléctrico neto a través de una superficie cerrada (llamada superficie gaussiana) es proporcional a la carga eléctrica neta encerrada dentro de dicha superficie.

## Fórmula General

$$\oint_S \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}$$

Donde:

- **$\oint_S$**: Integral de superficie cerrada.
- **$E$**: Campo eléctrico.
- **$d\vec{A}$**: Vector área (perpendicular a la superficie).
- **$Q_{\text{enc}}$**: Carga total neta dentro de la superficie.
- **$\epsilon_0$**: Permitividad del vacío.

## ¿Por qué es tan importante?

A diferencia de la [[Ley de Coulomb|ley de Coulomb]], que requiere integrar sobre todas las distribuciones de carga (a menudo complejo), la Ley de Gauss permite **determinar el campo eléctrico** simplemente seleccionando una superficie adecuada donde la simetría haga que el campo sea constante.

## Pasos para resolver problemas

Para aplicar Gauss, se deben seguir estos pasos:

1. **Identificar la simetría**:
    
    - **Esférica**: Usar una esfera gaussiana (para cargas puntuales o esferas cargadas).
    - **Cilíndrica**: Usar un cilindro gaussiano (para cables infinitos o cilindros).
    - **Plana**: Usar una "caja" o cilindro gaussiano (para planos infinitos).
2. **Dibujar la superficie gaussiana**: Debe pasar por el punto donde quieres calcular el campo y respetar la simetría de la distribución.
3. **Calcular el flujo**: Aprovechar que, por simetría, $\vec{E}$ es constante sobre la superficie.
4. **Despejar $E$**: Igualar el flujo calculado a $Q_{\text{enc}} / \epsilon_0$.

## Consideraciones clave

- **La superficie es imaginaria**: No tiene que existir físicamente; es una herramienta matemática.
- **Solo importa la carga interior**: Las cargas fuera de la superficie gaussiana no contribuyen al flujo neto a través de ella (aunque sí afectan el campo eléctrico local en cada punto).
- **Simetría**: Si no hay simetría alta (esférica, cilíndrica o plana), la ley de Gauss sigue siendo cierta, pero es inútil para calcular el campo de forma sencilla.

---

# **Vínculos relacionados:**

- [[Flujo Eléctrico]]
- [[Campo Eléctrico]]
- [[Ley de Coulomb]]