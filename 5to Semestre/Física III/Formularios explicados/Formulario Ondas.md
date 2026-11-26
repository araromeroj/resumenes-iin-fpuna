## 1. Ondas Mecánicas en Cuerdas

| Nombre / Concepto | Fórmula | Uso / Descripción |
| :--- | :--- | :--- |
| **Densidad lineal de masa** | $\mu = \frac{m}{L}$ | Calcula la masa por unidad de longitud de la cuerda. |
| **Densidad lineal (geometría)** | $\mu = \rho A = \rho \pi \frac{d^2}{4}$ | Expresa $\mu$ según densidad volumétrica $\rho$, área $A$ o diámetro $d$. |
| **Aproximación de ángulos pequeños** | $\sin\theta \approx \tan\theta \approx \frac{\partial y}{\partial x}$ | Simplifica el modelo dinámico para amplitudes pequeñas. |
| **Ecuación unidimensional de onda** | $\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial t^2}$ | Ecuación diferencial parcial de la propagación de onda. |
| **Rapidez en cuerda tensa** | $v = \sqrt{\frac{T}{\mu}}$ | Calcula la rapidez de la onda en función de la tensión $T$ y la densidad $\mu$. |
| **Fuerza transversal de tensión** | $F_y = -T \frac{\partial y}{\partial x}$ | Componente vertical de la fuerza restauradora en la cuerda. |
| **Velocidad transversal de partícula** | $u_y = \frac{\partial y}{\partial t}$ | Velocidad de oscilación del elemento de cuerda (eje $y$). |
| **Potencia instantánea general** | $P(x,t) = -T \frac{\partial y}{\partial x} \frac{\partial y}{\partial t}$ | Flujo instantáneo de energía mecánica en una posición $x$ y tiempo $t$. |
| **Potencia instantánea senoidal** | $P(x,t) = \mu v \omega^2 y_m^2 \cos^2(kx - \omega t - \phi)$ | Potencia en un punto para una onda armónica transversal. |
| **Energía por longitud de onda** | $E_\lambda = \frac{1}{2} \mu \omega^2 A^2 \lambda$ | Energía mecánica total contenida en una longitud de onda $\lambda$. |
| **Potencia media transportada** | $P_{\text{med}} = \frac{1}{2} \mu \omega^2 y_m^2 v$ | Promedio temporal de la energía transmitida por segundo. |
| **Potencia media (por tensión)** | $P_{\text{med}} = \frac{1}{2} \sqrt{T \mu} \omega^2 y_m^2$ | Potencia media expresada directamente en función de $T$. |
| **Rapidez por deformación elástica** | $v = \sqrt{\frac{Y}{\rho} \frac{\Delta L}{L}}$ | Rapidez cuando la tensión proviene de deformación térmica/mecánica. |
| **Tiempo de tránsito (soga libre)** | $\Delta t = 2 \sqrt{\frac{L}{g}}$ | Tiempo para que un pulso recorra una soga suspendida por su propio peso. |
| **Tiempo de tránsito (soga + masa $M$)** | $\Delta t = 2 \sqrt{\frac{L}{mg}} \left(\sqrt{M+m} - \sqrt{M}\right)$ | Tiempo de pulso en soga de masa $m$ que sostiene un cuerpo $M$. |
| **Intensidad de onda esférica** | $I = \frac{P}{4\pi r^2}$ | Potencia recibida por unidad de área a una distancia radial $r$. |
| **Ley del inverso del cuadrado** | $\frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}$ | Relación de intensidades entre dos distancias $r_1$ y $r_2$. |

---

## 2. Ondas Sonoras

| Nombre / Concepto | Fórmula | Uso / Descripción |
| :--- | :--- | :--- |
| **Función de onda de desplazamiento** | $s(x,t) = s_{\text{máx}} \cos(kx - \omega t)$ | Posición oscilatoria de las partículas del medio gaseoso/líquido. |
| **Función de onda de presión** | $\Delta p(x,t) = \Delta p_{\text{máx}} \sin(kx - \omega t)$ | Fluctuación de la presión en el medio respecto al equilibrio. |
| **Amplitud de variación de presión** | $\Delta p_{\text{máx}} = \rho v \omega s_{\text{máx}} = B k s_{\text{máx}}$ | Relación entre la amplitud de presión y la amplitud de desplazamiento. |
| **Rapidez del sonido en sólidos** | $v = \sqrt{\frac{Y}{\rho}}$ | Velocidad del sonido en barras sólida en función del Módulo de Young. |
| **Rapidez del sonido en fluidos** | $v = \sqrt{\frac{B}{\rho}}$ | Velocidad en fluidos según el Módulo de Compresibilidad Volumétrico $B$. |
| **Rapidez en gases ideales** | $v = \sqrt{\frac{\gamma R T}{M}}$ | Rapidez en gases según temperatura absoluta $T$ y masa molar $M$. |
| **Rapidez en el aire vs temperatura** | $v = 331 \sqrt{1 + \frac{T_C}{273}}$ | Rapidez aproximada del sonido en aire según $T_C$ en ${}^\circ\text{C}$. |
| **Intensidad de onda sonora** | $I = \frac{1}{2} \rho v \omega^2 s_{\text{máx}}^2 = \frac{(\Delta p_{\text{máx}})^2}{2\rho v}$ | Energía media por unidad de área y tiempo ($W/m^2$). |
| **Intensidad de fuente esférica** | $I = \frac{P_{\text{prom}}}{4\pi r^2}$ | Intensidad sonora distribuida en una esfera de radio $r$. |
| **Nivel sonoro (Decibeles)** | $\beta = 10 \log_{10}\left(\frac{I}{I_0}\right)$ | Nivel de intensidad en dB, con $I_0 = 10^{-12}\text{ W/m}^2$. |
| **Diferencia de niveles sonoros** | $\beta_2 - \beta_1 = 20 \log_{10}\left(\frac{r_1}{r_2}\right)$ | Cambio de nivel sonoro entre distancias $r_1$ y $r_2$. |
| **Atenuación por el medio** | $\beta(r) = \beta_{\text{teórico}}(r) - \alpha \cdot r$ | Corrección por absorción media del medio ($\alpha$ en $\text{dB/km}$). |
| **Efecto Doppler (Observador móvil)** | $f' = f \left(\frac{v \pm v_O}{v}\right)$ | Frecuencia percibida con observador acercándose ($+$) o alejándose ($-$). |
| **Efecto Doppler (Fuente móvil)** | $f' = f \left(\frac{v}{v \mp v_F}\right)$ | Frecuencia percibida con fuente acercándose ($-$) o alejándose ($+$). |
| **Efecto Doppler General** | $f' = f \left(\frac{v + v_O}{v - v_F}\right)$ | Ecuación general cuando ambos cuerpos están en movimiento. |
| **Longitud de onda modificada** | $\lambda' = \frac{v \mp v_F}{f}$ | Distancia entre frentes de onda comprimidos o expandidos. |
| **Rapidez máxima de fuente en MAS** | $v_{F,\text{máx}} = \omega_{\text{MAS}} A = \sqrt{\frac{k}{m}} A$ | Rapidez máxima empleada para calcular las frecuencias extremas en Doppler. |

---

## 3. Ondas Electromagnéticas

| Nombre / Concepto | Fórmula | Uso / Descripción |
| :--- | :--- | :--- |
| **Ley de Gauss Eléctrica** | $\oint \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}$ | Relaciona el flujo eléctrico cerrado con la carga neta encerrada. |
| **Ley de Gauss Magnética** | $\oint \vec{B} \cdot d\vec{A} = 0$ | Confirma la inexistencia de monopolos magnéticos. |
| **Ley de Ampère-Maxwell** | $\oint \vec{B} \cdot d\vec{l} = \mu_0 \left(i_c + \epsilon_0 \frac{d\Phi_E}{dt}\right)$ | El campo magnético es originado por corrientes y por $\frac{d\Phi_E}{dt}$. |
| **Ley de Faraday** | $\oint \vec{E} \cdot d\vec{l} = -\frac{d\Phi_B}{dt}$ | La variación del flujo magnético induce un campo eléctrico. |
| **Ecuación diferencial de onda ($E$)** | $\frac{\partial^2 E_y}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 E_y}{\partial t^2}$ | Ecuación de propagación para la componente del campo eléctrico. |
| **Ecuación diferencial de onda ($B$)** | $\frac{\partial^2 B_z}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 B_z}{\partial t^2}$ | Ecuación de propagación para la componente del campo magnético. |
| **Rapidez de la luz en el vacío** | $c = \frac{1}{\sqrt{\epsilon_0 \mu_0}} \approx 3.00 \times 10^8\text{ m/s}$ | Velocidad constante de propagación de ondas EM en el vacío. |
| **Relación de magnitudes instantáneas** | $E = c B \implies E_{\text{máx}} = c B_{\text{máx}}$ | Proporción estricta en todo instante entre las magnitudes de $\vec{E}$ y $\vec{B}$. |
| **Onda senoidal de campo eléctrico** | $\vec{E}(x,t) = \hat{j} E_{\text{máx}} \cos(kx \mp \omega t)$ | Expresión armónica para el campo eléctrico en la dirección $y$. |
| **Onda senoidal de campo magnético** | $\vec{B}(x,t) = \hat{k} B_{\text{máx}} \cos(kx \mp \omega t)$ | Expresión armónica para el campo magnético en la dirección $z$. |
| **Rapidez de onda en la materia** | $v = \frac{1}{\sqrt{\epsilon \mu}} = \frac{c}{\sqrt{K K_m}}$ | Velocidad de la luz dentro de un medio dieléctrico transparente. |
| **Índice de refracción** | $n = \frac{c}{v} = \sqrt{K K_m} \approx \sqrt{K}$ | Factor de reducción de la rapidez de la luz en la materia. |
| **Relación Cinemática EM** | $c = f \lambda = \frac{\omega}{k}$ | Conecta la frecuencia, longitud de onda y velocidad de la luz. |
| **Densidad total de energía ($u$)** | $u = \epsilon_0 E^2 = \frac{B^2}{\mu_0}$ | Energía por unidad de volumen almacenada en el campo EM. |
| **Vector de Poynting** | $\vec{S} = \frac{1}{\mu_0} \vec{E} \times \vec{B}$ | Vector de flujo instantáneo de energía por unidad de área. |
| **Módulo instantáneo de Poynting** | $S = \frac{EB}{\mu_0} = \frac{E^2}{\mu_0 c} = \epsilon_0 c E^2$ | Valor instantáneo de la potencia por metro cuadrado ($W/m^2$). |
| **Intensidad de radiación ($I$)** | $I = S_{\text{prom}} = \frac{E_{\text{máx}} B_{\text{máx}}}{2\mu_0} = \frac{1}{2}\epsilon_0 c E_{\text{máx}}^2$ | Promedio temporal del flujo de energía para ondas armónicas. |
| **Presión de radiación (Absorción)** | $p_{\text{rad}} = \frac{I}{c}$ | Presión ejercida sobre superficies perfectamente absorbentes. |
| **Presión de radiación (Reflexión)** | $p_{\text{rad}} = \frac{2I}{c}$ | Presión ejercida sobre superficies perfectamente reflectantes. |
| **Fuerza por presión de radiación** | $F = p_{\text{rad}} \cdot A$ | Fuerza ejercida por la radiación sobre una superficie de área $A$. |
