# Resumen Completo de Física III: Ondas Mecánicas y en Cuerdas

---

## 1. Modelo Físico e Hipótesis para Ondas en Cuerdas

Para analizar la propagación de una onda transversal a lo largo de una cuerda tensa, se considera un elemento infinitesimal de cuerda de longitud en equilibrio $\Delta x$ y masa $\Delta m$.

### Hipótesis del Modelo Ideal
1. **Flexibilidad:** La cuerda no ofrece resistencia a la flexión.
2. **Uniformidad:** La masa se distribuye homogéneamente con una **densidad lineal de masa** constante:
   $$\mu = \frac{m}{L} = \frac{\Delta m}{\Delta x}$$
3. **Tensión constante:** La cuerda está sometida a una tensión de magnitud aproximadamente constante $T$ (o $F$).
4. **Pequeños desplazamientos (Aproximación de ángulos pequeños):** La amplitud de la onda es pequeña en comparación con la longitud de onda. Para la pendiente $\theta$ de la cuerda en cualquier punto:
   $$\sin\theta \approx \tan\theta \approx \theta \approx \frac{\partial y}{\partial x}$$
   $$\cos\theta \approx 1$$

---

## 2. Equilibrio Dinámico y Deducción de la Ecuación de Onda

### Componente Horizontal
En la dirección del eje $x$, no hay aceleración apreciable:
$$\sum F_x = T_2 \cos\theta_2 - T_1 \cos\theta_1 \approx 0$$
Dado que $\cos\theta_1 \approx \cos\theta_2 \approx 1$, la tensión horizontal es uniforme a lo largo de toda la cuerda:
$$T_1 \approx T_2 \approx T$$

### Componente Transversal (Eje $y$)
La fuerza neta en la dirección vertical acciona la aceleración transversal de la masa del elemento $\Delta m$:
$$\sum F_y = T \sin\theta_2 - T \sin\theta_1 = \Delta m \cdot a_y$$

Aplicando la aproximación $\sin\theta \approx \tan\theta = \frac{\partial y}{\partial x}$:
$$T \left( \left.\frac{\partial y}{\partial x}\right|_{x+\Delta x} - \left.\frac{\partial y}{\partial x}\right|_x \right) = \Delta m \frac{\partial^2 y}{\partial t^2}$$

Sustituyendo $\Delta m = \mu \Delta x$ y dividiendo entre $\Delta x$:
$$T \frac{\left.\frac{\partial y}{\partial x}\right|_{x+\Delta x} - \left.\frac{\partial y}{\partial x}\right|_x}{\Delta x} = \mu \frac{\partial^2 y}{\partial t^2}$$

Tomando el límite cuando $\Delta x \to 0$, el término del lado izquierdo se convierte en la derivada parcial de segundo orden respecto a $x$:
$$T \frac{\partial^2 y}{\partial x^2} = \mu \frac{\partial^2 y}{\partial t^2} \implies \frac{\partial^2 y}{\partial x^2} = \frac{\mu}{T} \frac{\partial^2 y}{\partial t^2}$$

### Comparación con la Ecuación Unidimensional General de Onda
La ecuación general de onda diferencial es:
$$\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial t^2}$$

Comparando términos se obtiene la **rapidez de propagación de la onda transversal**:
$$v = \sqrt{\frac{T}{\mu}}$$

---

## 3. Deducción por Teorema del Impulso y Cantidad de Movimiento

Alternativamente, al aplicar una fuerza constante $F_y$ en el extremo de una cuerda con tensión longitudinal $F$:
1. **Relación geométrica de triángulos semejantes:**
   $$\frac{F_y}{F} = \frac{v_y t}{v t} \implies F_y = F \frac{v_y}{v}$$
2. **Masa en movimiento al tiempo $t$:**
   $$m = \mu v t$$
3. **Cantidad de movimiento transversal:**
   $$p_y = m v_y = \mu v t v_y$$
4. **Igualando el Impulso al cambio de Cantidad de Movimiento ($F_y t = p_y$):**
   $$\left(F \frac{v_y}{v}\right) t = \mu v t v_y \implies v = \sqrt{\frac{F}{\mu}}$$

### Principio General para Ondas Mecánicas
Para cualquier onda mecánica, la rapidez responde a la estructura general:
$$v = \sqrt{\frac{\text{Propiedad Elástica (Fuerza de restitución)}}{\text{Propiedad Inercial (Resistencia al retorno)}}}$$

---

## 4. Casos Especiales y Formulaciones Específicas de Ejercicios

1. **Relación con Densidad Volumétrica ($\rho$) y Geometría:**
   $$\mu = \rho \cdot A = \rho \cdot \pi \frac{d^2}{4}$$
   Donde $d$ es el diámetro del alambre y $A$ la sección transversal.

2. **Tensión por Deformación Elástica / Térmica (Módulo de Young $Y$):**
   La tensión elástica ejercida por la ley de Hooke es $T = Y A \frac{\Delta L}{L}$. Sustituyendo en la rapidez:
   $$v = \sqrt{\frac{Y A \frac{\Delta L}{L}}{\rho A}} = \sqrt{\frac{Y}{\rho} \frac{\Delta L}{L}}$$

3. **Cuerda Vertical Suspendida por su Propio Peso:**
   - Tensión variable a una distancia $x$ del extremo inferior: $T(x) = \mu x g$.
   - Rapidez en función de la posición: $v(x) = \sqrt{\frac{\mu x g}{\mu}} = \sqrt{g x}$.
   - Tiempo de tránsito total para recorrer una longitud $L$:
     $$\Delta t = \int_0^L \frac{dx}{v(x)} = \int_0^L \frac{dx}{\sqrt{gx}} = 2 \sqrt{\frac{L}{g}}$$

4. **Cuerda Vertical Suspendida con Masa Puntual $M$ en el Extremo:**
   - Tensión local: $T(x) = (M + \mu x)g$.
   - Tiempo de tránsito del pulso:
     $$\Delta t = 2 \sqrt{\frac{L}{m g}} \left(\sqrt{M+m} - \sqrt{M}\right)$$
   - Si $m \ll M$ (cuerda de masa despreciable): $\Delta t \approx \sqrt{\frac{m L}{M g}}$.

5. **Aceleración del Sistema (p. ej., Helicóptero acelerando verticalmente hacia arriba con aceleración $a$):**
   La gravedad efectiva pasa a ser $g_{\text{efectiva}} = g + a$, por lo que la tensión en la base de la carga o cable incrementa en proporción a la aceleración.

---

## 5. Energía, Potencia e Intensidad en Ondas

### Componentes dinámicas transversales
- **Fuerza transversal ejercida por la tensión:**
  $$F_y = -T \frac{\partial y}{\partial x}$$
- **Velocidad transversal del elemento de cuerda:**
  $$u_y = \frac{\partial y}{\partial t}$$

### Energía en una Longitud de Onda ($\lambda$)
Para una onda sinusoidal $y(x,t) = A \sin(kx - \omega t)$:
- **Energía Cinética en una longitud de onda:**
  $$K_\lambda = \frac{1}{4} \mu \omega^2 A^2 \lambda$$
- **Energía Potencial en una longitud de onda:**
  $$U_\lambda = \frac{1}{4} \mu \omega^2 A^2 \lambda$$
- **Energía Total en una longitud de onda:**
  $$E_\lambda = K_\lambda + U_\lambda = \frac{1}{2} \mu \omega^2 A^2 \lambda$$

### Potencia Transmitida por una Onda
- **Potencia Instantánea:**
  $$P(x,t) = -F_y u_y = T \frac{\partial y}{\partial x} \frac{\partial y}{\partial t}$$
  Para una onda armónica $y(x,t) = y_m \sin(kx - \omega t - \phi)$:
  $$P(x,t) = T k \omega y_m^2 \cos^2(kx - \omega t - \phi) = \mu v \omega^2 y_m^2 \cos^2(kx - \omega t - \phi)$$

- **Potencia Media ($P_{\text{med}}$):**
  Como el valor promedio del $\cos^2(\theta)$ en un ciclo es $\frac{1}{2}$:
  $$P_{\text{med}} = \frac{1}{2} \mu \omega^2 y_m^2 v = \frac{1}{2} \sqrt{T \mu} \omega^2 y_m^2$$

  *Proporcionalidades:* $P_{\text{med}} \propto \omega^2$, $P_{\text{med}} \propto y_m^2$, $P_{\text{med}} \propto v$.

### Intensidad de Ondas Tridimensionales
- **Intensidad ($I$):** Potencia media transmitida por unidad de área perpendicular a la dirección de propagación ($W/m^2$).
  $$I = \frac{P_{\text{med}}}{A}$$
- **Para una fuente puntual isotrópica (Ondas Esféricas):**
  $$I = \frac{P}{4 \pi r^2}$$
- **Ley del Inverso del Cuadrado:**
  $$\frac{I_1}{I_2} = \frac{r_2^2}{r_1^2} \implies I_1 r_1^2 = I_2 r_2^2$$

---

## 6. Formulario Completo Explicado

| Concepto / Nombre de Ecuación | Fórmula | Explicación |
| :--- | :--- | :--- |
| **Densidad Lineal de Masa** | $\mu = \frac{m}{L}$ | Masa por unidad de longitud de la cuerda. Propiedad inercial del medio. |
| **Relación con Densidad Volumétrica** | $\mu = \rho \cdot A = \rho \pi \frac{d^2}{4}$ | Expresa la densidad lineal en función de la densidad del material $\rho$, área $A$ o diámetro $d$. |
| **Aproximación de Ángulos Pequeños** | $\sin\theta \approx \tan\theta \approx \frac{\partial y}{\partial x}$ | Válida para pendientes transversales pequeñas ($\cos\theta \approx 1$). |
| **Ecuación Unidimensional de Onda** | $\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial t^2}$ | Ecuación diferencial parcial que rige la propagación de ondas mecánicas en una dimensión. |
| **Rapidez de Onda en una Cuerda** | $v = \sqrt{\frac{T}{\mu}}$ | Rapidez de propagación en función de la tensión $T$ (o $F$) y la densidad lineal $\mu$. |
| **Fuerza Transversal de la Tensión** | $F_y = -T \frac{\partial y}{\partial x}$ | Componente vertical de la fuerza ejercida por la tensión sobre un punto de la cuerda. |
| **Velocidad Transversal de Partícula** | $u_y = v_y = \frac{\partial y}{\partial t}$ | Velocidad de oscilación vertical del elemento de cuerda (diferente de $v$). |
| **Potencia Instantánea Transmitida** | $P(x,t) = -T \frac{\partial y}{\partial x} \frac{\partial y}{\partial t}$ | Rapidez instantánea con la que la onda transfiere energía mecánica en $(x,t)$. |
| **Potencia Instantánea Senoidal** | $P(x,t) = \mu v \omega^2 y_m^2 \cos^2(kx - \omega t - \phi)$ | Potencia instantánea para una onda armónica transversal que viaja en $+x$. |
| **Energía por Longitud de Onda** | $E_\lambda = \frac{1}{2} \mu \omega^2 A^2 \lambda$ | Suma de la energía cinética ($K_\lambda$) y potencial ($U_\lambda$) contenidas en una longitud $\lambda$. |
| **Potencia Media Transportada** | $P_{\text{med}} = \frac{1}{2} \mu \omega^2 y_m^2 v$ | Promedio temporal de la potencia. Proporcional al cuadrado de la amplitud y la frecuencia. |
| **Potencia Media (Función de Tensión)** | $P_{\text{med}} = \frac{1}{2} \sqrt{T \mu} \omega^2 y_m^2$ | Forma equivalente de la potencia media expresada mediante la tensión $T$. |
| **Rapidez por Módulo de Elasticidad** | $v = \sqrt{\frac{Y}{\rho} \frac{\Delta L}{L}}$ | Rapidez de onda cuando la tensión proviene de la deformación elástica/térmica del alambre. |
| **Tiempo de Tránsito (Cuerda Colgada)** | $\Delta t = 2 \sqrt{\frac{L}{g}}$ | Tiempo para que un pulso recorra una soga colgada verticalmente sujeta solo a su propio peso. |
| **Tiempo de Tránsito (Cuerda + Masa $M$)** | $\Delta t = 2 \sqrt{\frac{L}{m g}} \left(\sqrt{M+m} - \sqrt{M}\right)$ | Tiempo de tránsito cuando la soga de masa $m$ sostiene una masa suspendida $M$ en su extremo inferior. |
| **Intensidad de Onda Esférica** | $I = \frac{P}{4 \pi r^2}$ | Potencia por unidad de área a una distancia radial $r$ de una fuente puntual en 3D. |
| **Ley del Inverso del Cuadrado** | $\frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}$ | Relación de intensidades a dos distancias distintas $r_1$ y $r_2$ de una fuente isotrópica. |