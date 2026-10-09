## 1. Teoría Fundamental de Ondas Mecánicas
- **Definición de Onda:** Perturbación que se propaga en el espacio y en el tiempo, transportando energía y cantidad de movimiento de una región a otra sin que exista un transporte neto de materia.
- **Requisitos de las Ondas Mecánicas:** Para existir y propagarse, una onda mecánica requiere de tres elementos fundamentales:
  1. Una fuente o perturbación inicial.
  2. Un medio material cuyas partículas puedan ser desplazadas o alteradas.
  3. Un mecanismo de interacción elástica o recíproca entre las partículas del medio para transmitir la perturbación a las regiones vecinas.
- **Clasificación por la Dirección del Movimiento:**
  - *Transversales:* El desplazamiento oscilatorio de las partículas del medio ocurre en dirección perpendicular a la dirección en la que viaja la onda (ejemplo: ondas en cuerdas tensas).
  - *Longitudinales:* El desplazamiento de las partículas del medio ocurre en la misma dirección (paralela) en la que se propaga la onda (ejemplo: ondas sonoras en fluidos o resortes).
- **Frentes de Onda y Rayos:** 
  - *Frente de Onda:* Conjunto de puntos del espacio que, en un instante determinado, se encuentran exactamente en la misma fase de oscilación (ejemplo: frentes planos o esféricos).
  - *Rayo:* Línea recta indicadora de la dirección de propagación de la onda, la cual es siempre perpendicular al frente de onda.
- **Cinemática del Pulso Viajero:** Un pulso que mantiene su forma inalterada a lo largo del tiempo se describe mediante $y(x,t) = f(x \mp vt)$. El argumento $x - vt$ indica propagación en el sentido positivo del eje $x$ ($+x$), mientras que $x + vt$ representa propagación en el sentido negativo ($-x$).
- **Diferencia entre Velocidad de Fase y Velocidad de Partícula:**
  - *Velocidad de Fase ($v$):* Rapidez constante con la que avanza el pulso o la forma de la perturbación a lo largo del medio.
  - *Velocidad Transversal de Partícula ($u_y$):* Rapidez instantánea con la que oscila un elemento de masa del medio alrededor de su posición fija de equilibrio. $u_y \neq v$.
---
## 2. Descripción Matemática y Ecuación Unidimensional de Onda
- **Ecuación Unidimensional de Onda:** Ecuación diferencial parcial de segundo orden que gobierna la propagación de cualquier onda mecánica sin dispersión:
  $$\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}$$
  Relaciona la curvatura espacial de la cuerda ($\partial^2 y/\partial x^2$) con la aceleración transversal del elemento de masa ($\partial^2 y/\partial t^2$).
- **Solución General (Principio de D'Alembert):** Toda función de la forma $y(x,t) = f(x - vt) + g(x + vt)$ satisface la ecuación de onda lineal, representando la superposición de dos ondas viajando en sentidos opuestos.
- **Ondas Armónicas o Periódicas:** Son generadas cuando la fuente realiza un Movimiento Armónico Simple (MAS). Su forma matemática es:
  $$y(x,t) = A \sin(kx \mp \omega t - \phi)$$
  donde $A$ es la amplitud máxima, $k$ es el número de onda, $\omega$ la frecuencia angular y $\phi$ la constante de fase inicial.
- **Interpretación Espacio-Temporal de la Fase:**
  - La fase $\Phi(x,t) = kx - \omega t - \phi$ determina el estado de oscilación.
  - La constante de fase $\phi$ equivale a un desplazamiento espacial de la gráfica de $\Delta x = \phi / k$, o a un retraso/adelanto temporal de $\Delta t = \phi / \omega$.
---
## 3. Modelo Dinámico de Ondas Transversales en Cuerdas
- **Hipótesis del Modelo Lineal:** Se asume una cuerda perfectamente flexible, uniforme con densidad lineal constante ($\mu$), bajo una tensión uniforme ($T$) y sufriendo desplazamientos transversales pequeños. Estas premisas justifican la aproximación de ángulos pequeños ($\sin\theta \approx \tan\theta \approx \partial y/\partial x$ y $\cos\theta \approx 1$).
- **Deducción Dinámica de la Velocidad:**
  - Aplicando la Segunda Ley de Newton ($\sum F_y = \Delta m \cdot a_y$) a un segmento de cuerda diferencial de longitud $\Delta x$ y masa $\Delta m = \mu \Delta x$, se obtiene:
    $$T \frac{\partial^2 y}{\partial x^2} = \mu \frac{\partial^2 y}{\partial t^2} \implies \frac{\partial^2 y}{\partial x^2} = \frac{\mu}{T}\frac{\partial^2 y}{\partial t^2}$$
  - Al comparar esta relación con la ecuación clásica de onda, se deduce la rapidez de propagación:
    $$v = \sqrt{\frac{T}{\mu}}$$
- **Estructura General de la Rapidez de Ondas Mecánicas:**
  En cualquier medio material, la rapidez de propagación responde a la forma intrínseca:
  $$v = \sqrt{\frac{\text{Propiedad Elástica (Fuerza Restauradora)}}{\text{Propiedad Inercial (Resistencia al Cambio)}}}$$
---
## 4. Energía, Potencia e Intensidad Ondulatoria
- **Energía en una Cuerda:**
  - Un elemento de masa diferencial $dm = \mu dx$ posee energía cinética $dK = \frac{1}{2}(\mu dx) u_y^2$ y energía potencial $dU$ debido a su deformación elástica.
  - Para una onda senoidal, la energía cinética total $K_\lambda$ y la energía potencial total $U_\lambda$ contenidas en una longitud de onda ($\lambda$) son iguales:
    $$K_\lambda = U_\lambda = \frac{1}{4}\mu \omega^2 A^2 \lambda$$
  - La energía mecánica total en una longitud de onda es:
    $$E_\lambda = \frac{1}{2}\mu \omega^2 A^2 \lambda$$
- **Potencia Transportada:**
  - *Potencia Instantánea ($P$):* Rapidez con la que la fuerza de tensión realiza trabajo a través de la cuerda:
    $$P(x,t) = -T \frac{\partial y}{\partial x} \frac{\partial y}{\partial t} = \mu v \omega^2 A^2 \cos^2(kx - \omega t - \phi)$$
  - *Potencia Media ($P_{\text{med}}$):* Promedio temporal de la potencia a lo largo de un ciclo completo (sabiendo que el valor promedio de $\cos^2$ es $1/2$):
    $$P_{\text{med}} = \frac{1}{2}\mu \omega^2 A^2 v = \frac{1}{2}\sqrt{T\mu}\omega^2 A^2$$
- **Dependencias de la Potencia Media:**
  - Proporcional al cuadrado de la amplitud ($P_{\text{med}} \propto A^2$).
  - Proporcional al cuadrado de la frecuencia angular ($P_{\text{med}} \propto \omega^2$).
  - Proporcional a la velocidad de propagación ($P_{\text{med}} \propto v$).
- **Intensidad Tridimensional ($I$):** Para ondas que se propagan en tres dimensiones, la intensidad se define como la potencia media transmitida por unidad de área perpendicular a la dirección de propagación ($I = P_{\text{med}} / A$).
  - Para una fuente puntual e isótropa, la intensidad a una distancia $r$ satisface la **Ley del Inverso del Cuadrado**:
    $$I = \frac{P_{\text{prom}}}{4\pi r^2} \implies \frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}$$
---
## 5. Formulario Completo Explicado
| Concepto / Nombre de Ecuación | Fórmula | Explicación |
| :--- | :--- | :--- |
| **Ecuación Unidimensional de Onda** | $\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}$ | Ecuación diferencial parcial de segundo orden que condiciona la propagación de cualquier onda mecánica en una dimensión espacial. |
| **Solución General de D'Alembert** | $y(x,t) = f(x - vt) + g(x + vt)$ | Expresión general que representa la superposición de dos ondas viajeras desplazándose en sentidos opuestos ($+x$ y $-x$). |
| **Función de Onda Armónica** | $y(x,t) = A \sin(kx \mp \omega t - \phi)$ | Describe la perturbación producida por una fuente en MAS. $A$: amplitud, $k$: número de onda, $\omega$: frecuencia angular, $\phi$: fase inicial. |
| **Frecuencia y Periodo** | $f = \frac{1}{T}$ | $T$ es el tiempo (s) invertido en completar un ciclo oscilatorio. $f$ es el número de ciclos por segundo (Hertz, Hz). |
| **Número de Onda Angular ($k$)** | $k = \frac{2\pi}{\lambda}$ | Indica el avance de la fase por unidad de distancia espacial ($\text{rad/m}$). $\lambda$ es la longitud de onda. |
| **Frecuencia Angular ($\omega$)** | $\omega = \frac{2\pi}{T} = 2\pi f$ | Indica la rapidez con que avanza la fase de la onda por unidad de tiempo ($\text{rad/s}$). |
| **Rapidez de Propagación ($v$)** | $v = \lambda f = \frac{\lambda}{T} = \frac{\omega}{k}$ | Velocidad de fase con la que viaja la forma del pulso a lo largo del medio material ($\text{m/s}$). |
| **Velocidad Transversal de Partícula** | $u_y = \frac{\partial y(x,t)}{\partial t}$ | Velocidad instantánea de un pequeño elemento de masa oscilando verticalmente alrededor de su posición de equilibrio. |
| **Aceleración Transversal de Partícula** | $a_y = \frac{\partial^2 y(x,t)}{\partial t^2}$ | Aceleración instantánea del elemento de masa del medio en dirección perpendicular a la propagación. |
| **Desplazamiento Espacial por Fase** | $\Delta x = \frac{\phi}{k}$ | Desplazamiento horizontal equivalente producido por la constante de fase inicial $\phi$. |
| **Desplazamiento Temporal por Fase** | $\Delta t = \frac{\phi}{\omega}$ | Retraso o adelanto en el tiempo equivalente asociado a la constante de fase inicial $\phi$. |
| **Rapidez de Onda en Cuerda** | $v = \sqrt{\frac{T}{\mu}}$ | Rapidez de la onda en función de la tensión $T$ ($\text{N}$) y la densidad lineal de masa $\mu$ ($\text{kg/m}$). |
| **Rapidez General de Onda Mecánica** | $v = \sqrt{\frac{\text{Propiedad Elástica}}{\text{Propiedad Inercial}}}$ | Principio general para calcular la rapidez de ondas mecánicas en cualquier medio deformable. |
| **Masa del Elemento Diferencial** | $dm = \mu \, dx$ | Masa de un segmento infinitesimal de cuerda de longitud $dx$. |
| **Energía Cinética por Longitud de Onda** | $K_\lambda = \frac{1}{4}\mu \omega^2 A^2 \lambda$ | Energía cinética total almacenada en un segmento de cuerda correspondiente a una longitud de onda completa. |
| **Energía Potencial por Longitud de Onda** | $U_\lambda = \frac{1}{4}\mu \omega^2 A^2 \lambda$ | Energía potencial elástica total almacenada en un segmento de cuerda de longitud $\lambda$. |
| **Energía Total por Longitud de Onda** | $E_\lambda = \frac{1}{2}\mu \omega^2 A^2 \lambda$ | Suma de las energías cinética y potencial contenidas en una longitud de onda completa. |
| **Potencia Instantánea General** | $P(x,t) = -T \frac{\partial y}{\partial x} \frac{\partial y}{\partial t}$ | Rapidez instantánea con la que la tensión transmite energía a través de una posición $x$ en el tiempo $t$. |
| **Potencia Instantánea Armónica** | $P(x,t) = \mu v \omega^2 A^2 \cos^2(kx - \omega t - \phi)$ | Forma trigonométrica de la potencia transmitida por una onda senoidal. |
| **Potencia Media Transportada** | $P_{\text{med}} = \frac{1}{2}\mu \omega^2 A^2 v = \frac{1}{2}\sqrt{T\mu}\omega^2 A^2$ | Promedio temporal de la energía por unidad de tiempo transmitida a lo largo de un ciclo completo ($\text{W}$). |
| **Intensidad Tridimensional General** | $I = \frac{P_{\text{prom}}}{A}$ | Potencia media propagada por unidad de área perpendicular a la dirección del flujo energético ($\text{W/m}^2$). |
| **Intensidad para Fuente Puntual Isótropa** | $I = \frac{P_{\text{prom}}}{4\pi r^2}$ | Intensidad de onda esférica producida por una fuente puntual emisora de potencia $P_{\text{prom}}$ a una distancia $r$. |
| **Ley del Inverso del Cuadrado** | $\frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}$ | Relación que compara las intensidades de una onda esférica a dos distancias distintas $r_1$ y $r_2$ de la fuente. |