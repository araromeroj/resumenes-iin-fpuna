- Modelado matemático (Decaimiento Radiactivo)
- Ecuaciones Diferenciales de Segundo Orden
- ED de Segundo Orden No Homogéneas (Reducción de Orden)
- Métodos de Resolución (Variables separables, exactas y EDPs)

## Modelado de Crecimiento y Decaimiento

Casi todos estos problemas (bacterias, radiactividad, enfriamiento) se rigen por una ED de primer orden: dtdy​=ky.
- **La Solución Estándar:** $y(t)=y_0​e^{kt}$.
    - $y_0$​: Cantidad inicial (cuando $t=0$).
    - $k$: Constante de proporcionalidad (si es negativa, hay decaimiento).
- **Concepto de Vida Media ($T_{\frac{1}{2}}$​):** Es el tiempo necesario para que la sustancia se reduzca a la mitad ($y=\frac{1}{2}​y_0​$). Siempre se cumple que $k=​\frac{ln(0.5)}{T_{\frac{1}{2}}}$​.
- **Estrategia:** Siempre usa los dos puntos de datos que te dan para armar un sistema de ecuaciones y despejar primero k y luego y0​.

## ED Lineales de Segundo Orden ($ay''+by'+cy=f(x)$)
Cuando la ecuación tiene y′′, el camino se divide en dos partes:
### A. La Homogénea ($y_c$​)
Buscar la solución cuando la ecuación es igual a 0. Usar la **Ecuación Característica**: $mr^2+br+c=0$.

1. **Raíces reales distintas:** $y_c​=C_1​e^{r_1​x}+C_2​e^{r_2​x}$

2. **Raíces reales iguales:** $y_c​=C_1​e^{rx}+C_2​xe^{rx}$

3. **Raíces complejas ($α±βi$):** $y_c​=e^{αx}(C_1​cosβx+C_2​sinβx)$

### B. La Particular ($y_p$​) - Método de Coeficientes Indeterminados

Si el lado derecho $f(x)$ es una función "amigable", se usa una solución similar:

- Si $f(x)=e^{kx}$→ proponer Aekx.

- Si $f(x)=polinomio$→ proponer un polinomio del mismo grado.

- **OJO:** Si la propuesta ya aparece en $y_c​$, se la multiplica por $x$ para evitar la dependencia lineal.