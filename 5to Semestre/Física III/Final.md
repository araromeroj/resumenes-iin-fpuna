# Formulario Completo de Física III (Edición Examen Final)

## 1. Movimiento Armónico Simple (MAS)

### Ecuaciones Fundamentales y Cinemática

* **Ecuación diferencial del MAS:**
  $$
  \frac{d^2x}{dt^2} + \omega^2 x = 0 \qquad \left(\text{donde } a = -\omega^2 x\right)
  $$

* **Posición en función del tiempo:**
  $$
  x(t) = A\sin(\omega t + \varphi) \quad \text{o} \quad x(t) = A\cos(\omega t + \varphi)
  $$

* **Velocidad en función del tiempo y de la posición:**
  $$
  v(t) = \frac{dx}{dt} = \omega A\cos(\omega t + \varphi) \qquad \text{y} \qquad v(x) = \pm\omega\sqrt{A^2 - x^2}
  $$

* **Aceleración en función del tiempo y de la posición:**
  $$
  a(t) = \frac{d^2x}{dt^2} = -\omega^2 A\sin(\omega t + \varphi) \qquad \text{y} \qquad a(x) = -\omega^2 x
  $$

* **Valores máximos:**
  $$
  v_{\max} = \omega A \qquad \text{y} \qquad a_{\max} = \omega^2 A
  $$

* **Relaciones de frecuencia y período:**
  $$
  \omega = 2\pi f = \frac{2\pi}{T} \qquad \implies \qquad T = \frac{1}{f} = \frac{2\pi}{\omega}
  $$

* **Amplitud y fase a partir de condiciones iniciales ($x_0, v_0$ en $t=0$):**
  * Para $x(t) = A\cos(\omega t + \varphi)$:
    $$
    A = \sqrt{x_0^2 + \left(\frac{v_0}{\omega}\right)^2} \qquad \text{y} \qquad \tan\varphi = -\frac{v_0}{\omega x_0}
    $$
  * Para $x(t) = A\sin(\omega t + \alpha)$:
    $$
    A = \sqrt{x_0^2 + \left(\frac{v_0}{\omega}\right)^2} \qquad \text{y} \qquad \tan\alpha = \frac{\omega x_0}{v_0}
    $$

### Energía en el MAS

* **Energía cinética ($K$):**
  $$
  K = \frac{1}{2}mv^2 = \frac{1}{2}m\omega^2(A^2 - x^2)
  $$

* **Energía potencial elástica ($U$):**
  $$
  U = \frac{1}{2}kx^2 = \frac{1}{2}m\omega^2 x^2
  $$

* **Energía mecánica total ($E$):**
  $$
  E = K + U = \frac{1}{2}kA^2 = \frac{1}{2}m\omega^2 A^2 = \text{constante}
  $$

### Casos Específicos de Osciladores (Presentaciones)

* **Sistema Masa–Resorte:**
  $$
  \omega = \sqrt{\frac{k}{m}} \qquad \implies \qquad T = 2\pi\sqrt{\frac{m}{k}}, \qquad f = \frac{1}{2\pi}\sqrt{\frac{k}{m}}
  $$

* **Cuerpo sobre plataforma oscilante sin deslizar:**
  $$
  f_{e,\max} = m a_{\max} \implies \mu_e m g = m \omega^2 A \implies \mu_{e,\min} = \frac{\omega^2 A}{g}
  $$

* **Péndulo Simple (ángulos pequeños $\theta \ll 1\text{ rad}$):**
  $$
  \omega = \sqrt{\frac{g}{L}} \qquad \implies \qquad T = 2\pi\sqrt{\frac{L}{g}}, \qquad f = \frac{1}{2\pi}\sqrt{\frac{g}{L}}
  $$

* **Péndulo Físico (ángulos pequeños $\theta \ll 1\text{ rad}$):**
  $$
  \omega = \sqrt{\frac{mgd}{I}} \qquad \implies \qquad T = 2\pi\sqrt{\frac{I}{mgd}}, \qquad L_{\text{eq}} = \frac{I}{md}
  $$
  *(Teorema de Steiner: $I = I_{CM} + md^2$. Momentos útiles: Varilla en CM $I_{CM} = \frac{1}{12}mL^2$; Disco $I_{CM} = \frac{1}{2}mR^2$; Anillo $I_{CM} = mR^2$).*

* **Péndulo Físico acoplado a un resorte (a distancia $h$ del pivote):**
  $$
  \omega = \sqrt{\frac{mgd + kh^2}{I}} \qquad \implies \qquad T = 2\pi\sqrt{\frac{I}{mgd + kh^2}}
  $$

* **Péndulo de Torsión (constante de torsión $\kappa$, torque $\tau = -\kappa\theta$):**
  $$
  \frac{d^2\theta}{dt^2} + \frac{\kappa}{I}\theta = 0 \qquad \implies \qquad \omega = \sqrt{\frac{\kappa}{I}}, \qquad T = 2\pi\sqrt{\frac{I}{\kappa}}
  $$

* **Bloque flotante oscilando verticalmente (altura $a$, densidad bloque $\rho$, densidad líquido $\rho_L$):**
  $$
  \omega = \sqrt{\frac{\rho_L g}{\rho a}} \qquad \implies \qquad T = 2\pi\sqrt{\frac{\rho a}{\rho_L g}}
  $$

* **Cilindro/Esfera rodando sin deslizar unido a un resorte:**
  $$
  \omega = \sqrt{\frac{k}{m + I_{CM}/R^2}}
  $$

## 2. Oscilaciones Amortiguadas

### Parámetros Comunes

* **Fuerza retardadora viscosa:**
  $$
  \vec{F}_R = -b\vec{v}
  $$
  *(Si se da la velocidad terminal $v_T$ en caída libre: $mg = b v_T \implies b = \frac{mg}{v_T}$ y $\gamma = \frac{g}{2v_T}$).*

* **Ecuación diferencial general:**
  $$
  m\frac{d^2x}{dt^2} + b\frac{dx}{dt} + kx = 0 \qquad \implies \qquad \frac{d^2x}{dt^2} + 2\gamma\frac{dx}{dt} + \omega_0^2 x = 0
  $$

* **Constante de amortiguamiento ($\gamma$) y frecuencia natural ($\omega_0$):**
  $$
  \gamma = \frac{b}{2m} \qquad \text{y} \qquad \omega_0 = \sqrt{\frac{k}{m}}
  $$

* **Parámetro característico ($q$):**
  $$
  q = \sqrt{\gamma^2 - \omega_0^2}
  $$

### Caso A: Movimiento Subamortiguado ($\gamma < \omega_0$)

*El sistema oscila con amplitud decreciente en el tiempo.*

* **Frecuencia angular amortiguada ($\omega_d$):**
  $$
  \omega_d = \sqrt{\omega_0^2 - \gamma^2} = \sqrt{\frac{k}{m} - \frac{b^2}{4m^2}}
  $$

* **Período amortiguado ($T_d$):**
  $$
  T_d = \frac{2\pi}{\omega_d} = \frac{2\pi}{\sqrt{\omega_0^2 - \gamma^2}}
  $$

* **Ecuación de posición $x(t)$:**
  $$
  x(t) = A_0 e^{-\gamma t}\cos(\omega_d t + \varphi_0) \quad \text{o} \quad x(t) = e^{-\gamma t}\left[C_1\cos(\omega_d t) + C_2\sin(\omega_d t)\right]
  $$

* **Amplitud envolvente y razón entre máximos sucesivos ($T_d$):**
  $$
  A(t) = A_0 e^{-\gamma t} \qquad \implies \qquad \frac{A(t + T_d)}{A(t)} = e^{-\gamma T_d}
  $$

* **Tiempo de vida media ($\tau$), energía disipada y pérdida fraccional por ciclo:**
  $$
  \tau = \frac{1}{2\gamma} = \frac{m}{b} \qquad \implies \qquad E(t) = E_0 e^{-t/\tau} = E_0 e^{-2\gamma t}
  $$
  $$
  \frac{\vert{}\Delta E\vert{}_{\text{ciclo}}}{E} = 1 - e^{-2\gamma T_d} \approx 2\gamma T_d \quad (\text{para amortiguamiento débil})
  $$

* **Factor de calidad ($Q$):**
  $$
  Q = 2\pi\frac{E}{\vert{}\Delta E\vert{}_{\text{ciclo}}} = \omega_d \tau = \frac{\omega_d}{2\gamma}
  $$

### Caso B: Movimiento Críticamente Amortiguado ($\gamma = \omega_0$, $q = 0$)

*El sistema regresa al equilibrio en el menor tiempo posible sin oscilar.*

* **Coeficiente de amortiguamiento crítico ($b_c$):**
  $$
  \gamma = \omega_0 \implies \frac{b_c}{2m} = \sqrt{\frac{k}{m}} \implies b_c = 2m\omega_0 = 2\sqrt{mk}
  $$

* **Ecuación de posición $x(t)$:**
  $$
  x(t) = e^{-\gamma t}(A_1 + A_2 t) = A_1 e^{-\gamma t} + A_2 t e^{-\gamma t}
  $$

* **Constantes a partir de condiciones iniciales ($x_0, v_0$ en $t=0$):**
  $$
  A_1 = x_0 \qquad \text{y} \qquad A_2 = v_0 + \gamma x_0
  $$

### Caso C: Movimiento Sobreamortiguado ($\gamma > \omega_0$, $q > 0$)

*Fricción muy elevada; el sistema no oscila y regresa lentamente al equilibrio.*

* **Ecuación de posición $x(t)$:**
  $$
  x(t) = A_1 e^{-(\gamma - q)t} + A_2 e^{-(\gamma + q)t} \qquad \left(\text{donde } q = \sqrt{\gamma^2 - \omega_0^2}\right)
  $$

* **Constantes a partir de condiciones iniciales ($x_0, v_0$ en $t=0$):**
  $$
  A_1 = \frac{v_0 + (\gamma + q)x_0}{2q} \qquad \text{y} \qquad A_2 = \frac{-v_0 - (\gamma - q)x_0}{2q}
  $$

## 3. Movimiento Forzado y Resonancia

* **Fuerza impulsora periódica:**
  $$
  F(t) = F_0 \cos(\omega_f t)
  $$

* **Ecuación diferencial del movimiento forzado:**
  $$
  m\frac{d^2x}{dt^2} + b\frac{dx}{dt} + kx = F_0\cos(\omega_f t) \qquad \implies \qquad \frac{d^2x}{dt^2} + 2\gamma\frac{dx}{dt} + \omega_0^2 x = \frac{F_0}{m}\cos(\omega_f t)
  $$

* **Solución completa (Transitoria + Estacionaria):**
  $$
  x(t) = x_{\text{trans}}(t) + x_{\text{est}}(t)
  $$
  * **Estado estacionario ($t \to \infty$):** $x_{\text{est}}(t) = A\cos(\omega_f t - \delta)$
  * **Estado transitorio ($t$ pequeño):** Toma la forma homogénea del amortiguamiento (ej. $C e^{-\gamma t}\cos(\omega_d t + \phi)$ si $\gamma < \omega_0$), calculando sus constantes con $x(0)$ y $v(0)$ sobre la suma total.

* **Amplitud en estado estacionario ($A$):**
  $$
  A = \frac{F_0 / m}{\sqrt{(\omega_0^2 - \omega_f^2)^2 + 4\gamma^2\omega_f^2}} = \frac{F_0}{\sqrt{(k - m\omega_f^2)^2 + b^2\omega_f^2}}
  $$

* **Ángulo de desfase ($\delta$):**
  $$
  \tan\delta = \frac{2\gamma\omega_f}{\omega_0^2 - \omega_f^2} = \frac{b\omega_f}{k - m\omega_f^2}
  $$
  * Si $\omega_f \ll \omega_0 \implies \delta \approx 0$
  * Si $\omega_f = \omega_0 \implies \delta = \frac{\pi}{2}$
  * Si $\omega_f \gg \omega_0 \implies \delta \to \pi$

* **Condición de Resonancia:**
  * **Frecuencia de resonancia exacta (amplitud máxima):**
    $$
    \omega_{\text{res}} = \sqrt{\omega_0^2 - 2\gamma^2} \qquad (\text{si } \omega_0^2 > 2\gamma^2)
    $$
  * **Para amortiguamiento débil ($\gamma \ll \omega_0$):**
    $$
    \omega_{\text{res}} \approx \omega_0 \qquad \implies \qquad A_{\max} \approx \frac{F_0}{2m\gamma\omega_0} = \frac{F_0}{b\omega_0}
    $$

* **Anchura de banda ($\Delta\omega$) y Factor de Calidad ($Q$):**
  $$
  \Delta\omega = \omega_2 - \omega_1 \approx 2\gamma = \frac{b}{m} \qquad \text{y} \qquad Q \approx \frac{\omega_0}{\Delta\omega} = \frac{\omega_0}{2\gamma}
  $$

## 4. Función de Onda y Ondas en Cuerdas

### Función de Onda General y Armónica

* **Forma general de una onda viajera:**
  $$
  \psi(x, t) = f(x \mp vt)
  $$
  *(Signo $-$: avanza hacia $+x$; signo $+$: avanza hacia $-x$).*

* **Ecuación diferencial unidimensional de onda:**
  $$
  \frac{\partial^2\psi}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2\psi}{\partial t^2}
  $$

* **Función de onda armónica (sinusoidal):**
  $$
  y(x, t) = A\sin(kx \mp \omega t + \varphi) \quad \text{o} \quad y(x, t) = A\cos(kx \mp \omega t + \varphi)
  $$

* **Parámetros de onda:**
  * **Número de onda angular ($k$):** $k = \frac{2\pi}{\lambda}$
  * **Frecuencia angular ($\omega$):** $\omega = \frac{2\pi}{T} = 2\pi f$
  * **Rapidez de propagación ($v$):** $v = \lambda f = \frac{\lambda}{T} = \frac{\omega}{k}$

### Ondas en Cuerdas Tensas

* **Densidad lineal de masa ($\mu$):**
  $$
  \mu = \frac{m}{L} = \rho A_{\text{sección}}
  $$

* **Rapidez de una onda transversal en una cuerda:**
  $$
  v = \sqrt{\frac{T}{\mu}}
  $$

* **Casos Especiales de Tensión en Cuerdas (Presentaciones):**
  * **Cuerda vertical de masa $m$ y longitud $L$ con bloque $M$ colgando en el extremo:**
    * Tensión a altura $y$ desde abajo: $T(y) = \left(M + \frac{m}{L}y\right)g$
    * Tiempo que tarda un pulso en recorrer toda la cuerda:
      $$
      \Delta t = \frac{2L}{mg}\left(\sqrt{M + m} - \sqrt{M}\right) \qquad \left(\text{Si } M = 0: \; \Delta t = 2\sqrt{\frac{L}{g}}\right)
      $$
  * **Alambre sometido a deformación elástica (Módulo de Young $Y$):**
    $$
    T = Y A_{\text{sección}} \frac{\Delta L}{L} \qquad \implies \qquad v = \sqrt{\frac{Y}{\rho}\frac{\Delta L}{L}}
    $$
  * **Masa sumergida en un líquido (Empuje $E = \rho_L V g$):**
    $$
    T_{\text{sumergida}} = W - E = (\rho_{\text{cuerpo}} - \rho_L) V g
    $$

* **Velocidad y aceleración transversal de un elemento de la cuerda:**
  $$
  v_y = \frac{\partial y}{\partial t} = \mp\omega A\cos(kx \mp \omega t + \varphi) \qquad \text{y} \qquad a_y = \frac{\partial^2 y}{\partial t^2} = -\omega^2 y
  $$
  *(Valores máximos: $v_{y,\max} = \omega A$, $a_{y,\max} = \omega^2 A$).*

* **Potencia promedio transmitida por la onda en una cuerda:**
  $$
  P_{\text{prom}} = \frac{1}{2}\mu v \omega^2 A^2
  $$

### Interferencia y Ondas Estacionarias en Cuerdas

* **Superposición de dos ondas iguales desfasadas en $\phi$:**
  $$
  y(x, t) = \left[2A\cos\left(\frac{\phi}{2}\right)\right]\sin\left(kx - \omega t + \frac{\phi}{2}\right)
  $$
  * **Interferencia constructiva:** $\Delta r = n\lambda \quad (n = 0, 1, 2, \dots)$
  * **Interferencia destructiva:** $\Delta r = \left(n + \frac{1}{2}\right)\lambda \quad (n = 0, 1, 2, \dots)$

* **Función de onda estacionaria:**
  $$
  y(x, t) = (2A\sin kx)\cos\omega t
  $$
  * **Posición de los nodos ($y=0$):** $x = n\frac{\lambda}{2} \quad (n = 0, 1, 2, \dots)$
  * **Posición de los antinodos ($y_{\max}$):** $x = (2n + 1)\frac{\lambda}{4} \quad (n = 0, 1, 2, \dots)$

* **Armónicos en una cuerda fija en ambos extremos (longitud $L$):**
  $$
  \lambda_n = \frac{2L}{n} \qquad \text{y} \qquad f_n = n f_1 = \frac{n}{2L}\sqrt{\frac{T}{\mu}} \qquad (n = 1, 2, 3, \dots)
  $$

## 5. Ondas de Sonido, Nivel Sonoro y Efecto Doppler

### Rapidez e Intensidad del Sonido

* **Rapidez del sonido en un fluido (módulo volumétrico $B$, densidad $\rho$):**
  $$
  v = \sqrt{\frac{B}{\rho}}
  $$

* **Rapidez del sonido en un sólido (módulo de Young $Y$):**
  $$
  v = \sqrt{\frac{Y}{\rho}}
  $$

* **Rapidez del sonido en el aire según la temperatura ($T$ en $^\circ\text{C}$):**
  $$
  v = 331\sqrt{1 + \frac{T}{273}}\text{ m/s} \approx (331 + 0,6\,T)\text{ m/s}
  $$

* **Relación entre amplitud de desplazamiento ($s_{\max}$) y amplitud de presión ($\Delta P_{\max}$):**
  $$
  \Delta P_{\max} = \rho v \omega s_{\max} = B k s_{\max}
  $$

* **Intensidad de una onda sonora ($I$):**
  $$
  I = \frac{P}{\Delta A} = \frac{1}{2}\rho v (\omega s_{\max})^2 = \frac{(\Delta P_{\max})^2}{2\rho v}
  $$

* **Intensidad de una onda esférica (fuente puntual de potencia $P$ a distancia $r$):**
  $$
  I = \frac{P}{4\pi r^2} \qquad \implies \qquad \frac{I_1}{I_2} = \left(\frac{r_2}{r_1}\right)^2
  $$

### Nivel Sonoro ($\beta$)

* **Nivel de intensidad sonora en decibeles ($\text{dB}$):**
  $$
  \beta = 10\log_{10}\left(\frac{I}{I_0}\right) \qquad \left(\text{donde } I_0 = 10^{-12}\text{ W/m}^2\right)
  $$

* **Despeje de la intensidad ($I$) a partir de $\beta$:**
  $$
  I = I_0 \cdot 10^{\beta / 10}
  $$

* **Diferencia de nivel sonoro y variación con la distancia:**
  $$
  \Delta\beta = \beta_2 - \beta_1 = 10\log_{10}\left(\frac{I_2}{I_1}\right) = 20\log_{10}\left(\frac{r_1}{r_2}\right)
  $$

* **Suma de niveles de múltiples fuentes incoherentes:**
  $$
  I_{\text{total}} = I_1 + I_2 + \dots + I_N = I_0\sum_{i=1}^N 10^{\beta_i/10} \qquad \implies \qquad \beta_{\text{total}} = 10\log_{10}\left(\frac{I_{\text{total}}}{I_0}\right)
  $$

### Efecto Doppler

* **Fórmula general:**
  $$
  f' = f\left(\frac{v \pm v_O}{v \mp v_F}\right)
  $$
  * $v$: Rapidez del sonido en el medio.
  * $v_O$: Rapidez del observador ($+$ si se acerca a la fuente, $-$ si se aleja).
  * $v_F$: Rapidez de la fuente ($-$ si se acerca al observador, $+$ si se aleja).

* **Casos Especiales de Efecto Doppler (Presentaciones):**
  * **Con viento de rapidez $v_w$:** Se reemplaza $v$ por $(v + v_w)$ si el viento sopla de la fuente hacia el observador, o por $(v - v_w)$ si sopla en sentido contrario.
  * **Reflexión en un objeto móvil (eco / radar):** Se aplica en dos etapas: el objeto recibe $f_1$ como observador móvil y luego reemite $f_1$ como fuente móvil hacia el detector original.

## 6. Ondas Electromagnéticas (OEM)

### Función de Onda y Propiedades en el Vacío y Medios

* **Ecuaciones de onda armónica para los campos $\vec{E}$ y $\vec{B}$ (propagación en $\pm x$):**
  $$
  \vec{E}(x, t) = \pm E_{\max}\cos(kx \mp \omega t)\,\hat{u}_E \qquad \text{y} \qquad \vec{B}(x, t) = \pm B_{\max}\cos(kx \mp \omega t)\,\hat{u}_B
  $$
  *(Regla direccional obligatoria: $\hat{u}_E \times \hat{u}_B = \hat{u}_{\text{propagación}}$).*

* **Rapidez de la luz en el vacío ($c$):**
  $$
  c = \frac{1}{\sqrt{\varepsilon_0 \mu_0}} = \frac{\omega}{k} = \lambda f \approx 3,00 \times 10^8\text{ m/s}
  $$

* **Rapidez de una OEM en un medio material e índice de refracción ($n$):**
  $$
  v = \frac{1}{\sqrt{\varepsilon\mu}} = \frac{c}{\sqrt{K_e K_m}} = \frac{c}{n} \qquad \implies \qquad n = \frac{c}{v} = \frac{\lambda_0}{\lambda_n}
  $$

* **Relación entre magnitudes de los campos en el vacío y en un medio:**
  * En el vacío: $\frac{E}{B} = \frac{E_{\max}}{B_{\max}} = c$
  * En un medio: $\frac{E}{B} = \frac{E_{\max}}{B_{\max}} = v = \frac{c}{n}$

### Vector de Poynting ($\vec{S}$) e Intensidad ($I$)

* **Vector de Poynting instantáneo (flujo de potencia por unidad de área):**
  $$
  \vec{S} = \frac{1}{\mu_0}(\vec{E} \times \vec{B})
  $$

* **Magnitud del Vector de Poynting instantáneo:**
  $$
  S = \frac{EB}{\mu_0} = \frac{E^2}{\mu_0 c} = \varepsilon_0 c E^2 = \frac{c}{\mu_0}B^2
  $$

* **Intensidad de la onda electromagnética (Vector de Poynting promedio $S_{\text{prom}}$):**
  $$
  I = S_{\text{prom}} = \frac{E_{\max} B_{\max}}{2\mu_0} = \frac{E_{\max}^2}{2\mu_0 c} = \frac{c B_{\max}^2}{2\mu_0} = \frac{1}{2}\varepsilon_0 c E_{\max}^2
  $$

* **Densidad de energía electromagnética ($u$):**
  * **Instantánea:** $u = u_E + u_B = \frac{1}{2}\varepsilon_0 E^2 + \frac{1}{2\mu_0}B^2 = \varepsilon_0 E^2 = \frac{B^2}{\mu_0}$
  * **Promedio:** $u_{\text{prom}} = \frac{1}{2}\varepsilon_0 E_{\max}^2 = \frac{B_{\max}^2}{2\mu_0} = \frac{I}{c}$

### Cantidad de Movimiento y Presión de Radiación

* **Cantidad de movimiento transportada ($\Delta p$) para energía ($U$):**
  * **Absorción total:** $\Delta p = \frac{U}{c}$
  * **Reflexión total:** $\Delta p = \frac{2U}{c}$

* **Presión de radiación ($p_{\text{rad}}$):**
  * **Superficie totalmente absorbente:**
    $$
    p_{\text{rad}} = \frac{I}{c} = \frac{S_{\text{prom}}}{c} = u_{\text{prom}}
    $$
  * **Superficie totalmente reflectante:**
    $$
    p_{\text{rad}} = \frac{2I}{c} = \frac{2S_{\text{prom}}}{c} = 2u_{\text{prom}}
    $$

* **Fuerza ejercida por la radiación sobre un área perpendicular ($A$):**
  $$
  F = p_{\text{rad}} \cdot A
  $$
  * **Absorción total:** $F = \frac{I \cdot A}{c} = \frac{P}{c}$
  * **Reflexión total:** $F = \frac{2I \cdot A}{c} = \frac{2P}{c}$

## 7. Constantes Físicas Fundamentales

* **Rapidez de la luz en el vacío:** $c = 3,00 \times 10^8\text{ m/s}$
* **Permeabilidad magnética del vacío:** $\mu_0 = 4\pi \times 10^{-7}\text{ T}\cdot\text{m/A}$
* **Permitividad eléctrica del vacío:** $\varepsilon_0 = 8,85 \times 10^{-12}\text{ C}^2/(\text{N}\cdot\text{m}^2)$
* **Intensidad sonora umbral de audición:** $I_0 = 10^{-12}\text{ W/m}^2$
* **Aceleración de la gravedad estándar:** $g = 9,8\text{ m/s}^2$ (o $9,81\text{ m/s}^2$)