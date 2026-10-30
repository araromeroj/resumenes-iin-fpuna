# Resumen Completo de Física III: Ondas Electromagnéticas

## 1. Las Ecuaciones de Maxwell y el Origen de las Ondas Electromagnéticas
Las ecuaciones de Maxwell sintetizan las leyes fundamentales del electromagnetismo y demuestran que un campo magnético variable en el tiempo induce un campo eléctrico (Ley de Faraday) y que un campo eléctrico variable induce un campo magnético (Ley de Ampère-Maxwell). Esta interacción acoplada permite la propagación de una perturbación electromagnética autosostenida a través del espacio, incluso en ausencia de un medio material.

### Las Cuatro Ecuaciones Fundamentales en el Vacío
1. **Ley de Gauss para el Campo Eléctrico:**
   $$\oint \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}$$
   Establece que las cargas eléctricas son las fuentes de las líneas de campo eléctrico.
2. **Ley de Gauss para el Magnetismo:**
   $$\oint \vec{B} \cdot d\vec{A} = 0$$
   Indica que no existen monopolos magnéticos aislados; las líneas de campo magnético son cerradas.
3. **Ley de Ampère-Maxwell:**
   $$\oint \vec{B} \cdot d\vec{l} = \mu_0 \left( i_c + \epsilon_0 \frac{d\Phi_E}{dt} \right)$$
   Muestra que los campos magnéticos son generados tanto por corrientes de conducción ($i_c$) como por campos eléctricos variables en el tiempo ($\epsilon_0 \frac{d\Phi_E}{dt}$, corriente de desplazamiento).
4. **Ley de Faraday:**
   $$\oint \vec{E} \cdot d\vec{l} = -\frac{d\Phi_B}{dt}$$
   Establece que un flujo magnético variable en el tiempo induce un campo eléctrico no conservativo.

### Origen de la Radiación Electromagnética
* Toda **carga eléctrica acelerada** irradia energía en forma de ondas electromagnéticas.
* Una forma habitual de generar una onda armónica continua es someter a una carga a un **Movimiento Armónico Simple (MAS)**, garantizando una aceleración continua en el tiempo.

## 2. Ecuación de Onda Diferencial y Rapidez de la Luz
Aplicando el operador rotacional (o circulaciones infinitesimales) a las Leyes de Faraday y Ampère-Maxwell en una región libre de cargas ($Q_{\text{enc}} = 0$) y corrientes de conducción ($i_c = 0$), se deducen las ecuaciones diferenciales parciales de onda de segundo orden.

### Ecuaciones Diferenciales para los Campos
Para una onda plana que se propaga en el eje $x$:
$$\frac{\partial^2 E_y}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 E_y}{\partial t^2}$$
$$\frac{\partial^2 B_z}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 B_z}{\partial t^2}$$

### Rapidez de Propagación en el Vacío ($c$)
Comparando estas expresiones con la ecuación unidimensional general de onda $\frac{\partial^2 f}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 f}{\partial t^2}$, se deduce que la rapidez de propagación es:
$$v = c = \frac{1}{\sqrt{\epsilon_0 \mu_0}} \approx 3.00 \times 10^8 \text{ m/s}$$
Donde:
* $\epsilon_0 \approx 8.854 \times 10^{-12} \text{ F/m}$: Permitividad eléctrica del vacío.
* $\mu_0 = 4\pi \times 10^{-7} \text{ T}\cdot\text{m/A}$: Permeabilidad magnética del vacío.

## 3. Propiedades de las Ondas Electromagnéticas Planas y Sinusoidales
1. **Onda Transversal:** Tanto el campo eléctrico $\vec{E}$ como el campo magnético $\vec{B}$ son perpendiculares entre sí y perpendiculares a la dirección de propagación de la onda.
2. **Dirección de Propagación:** Coincide con la dirección del producto vectorial $\vec{E} \times \vec{B}$.
3. **Relación entre Magnitudes:** En todo instante y en cualquier punto del espacio, las magnitudes de los campos guardan una proporción constante igual a la rapidez de la luz:
   $$E = c B \quad \implies \quad E_{\text{máx}} = c B_{\text{máx}}$$
4. **Propagación en el Vacío:** No requieren un medio material para transmitirse (lo que oscila son los propios campos en el espacio).

### Funciones de Onda Sinusoidales
Para una onda linealmente polarizada que viaja en la dirección $+x$:
$$\vec{E}(x,t) = \hat{j} E_{\text{máx}} \cos(kx - \omega t - \phi)$$
$$\vec{B}(x,t) = \hat{k} B_{\text{máx}} \cos(kx - \omega t - \phi)$$
* **Fase:** Los campos $\vec{E}$ y $\vec{B}$ están **en fase** (alcanzan sus máximos, mínimos y ceros de manera simultánea).

## 4. Propagación en la Materia e Índice de Refracción
Cuando una onda electromagnética se propaga a través de un material dieléctrico (no conductor y transparente):
* La permitividad eléctrica del medio es $\epsilon = K \epsilon_0$ (donde $K$ es la constante dieléctrica).
* La permeabilidad magnética del medio es $\mu = K_m \mu_0$ (donde $K_m$ es la permeabilidad relativa, frecuentemente $K_m \approx 1$).

### Rapidez en un Medio Material ($v$)
$$v = \frac{1}{\sqrt{\epsilon \mu}} = \frac{1}{\sqrt{K K_m \epsilon_0 \mu_0}} = \frac{c}{\sqrt{K K_m}}$$

### Índice de Refracción ($n$)
Se define como la razón entre la rapidez de la luz en el vacío y la rapidez en el medio:
$$n = \frac{c}{v} = \sqrt{K K_m} \approx \sqrt{K}$$
Dado que $K > 1$, la velocidad de una onda electromagnética en la materia siempre es menor que en el vacío ($v < c$).

## 5. El Espectro Electromagnético
El espectro electromagnético abarca todas las frecuencias y longitudes de onda posibles. La relación entre frecuencia ($f$), longitud de onda ($\lambda$) y rapidez ($c$) es:
$$c = f \cdot \lambda$$

### Regiones del Espectro (de menor a mayor frecuencia)
1. **Ondas de Radio ($\lambda > 0.1\text{ m}$, $f < 3\text{ GHz}$):** Producidas por cargas aceleradas en antenas y circuitos osciladores LC. Utilizadas en telecomunicaciones.
2. **Microondas ($10^{-4}\text{ m} < \lambda < 0.3\text{ m}$):** Generadas por dispositivos electrónicos especiales (como magnetrones). Utilizadas en radar y calefacción molecular (hornos).
3. **Infrarrojo ($700\text{ nm} < \lambda < 1\text{ mm}$):** Emitidas por cuerpos calientes y moléculas debido a agitación térmica. Se perciben como radiación de calor.
4. **Luz Visible ($400\text{ nm} \le \lambda \le 700\text{ nm}$):** Región detectable por el ojo humano. Producida por reorganización de electrones en átomos y moléculas.
   * *Rojo:* $\lambda \approx 700\text{ nm}$
   * *Naranja / Amarillo / Verde:* $\lambda \approx 550\text{ nm}$ (sensibilidad máxima del ojo)
   * *Azul / Violeta:* $\lambda \approx 400\text{ nm}$
5. **Ultravioleta ($0.6\text{ nm} < \lambda < 400\text{ nm}$):** Proveniente principalmente del Sol. Absorbe gran parte la capa de ozono ($O_3$). Causa quemaduras solares.
6. **Rayos X ($10^{-12}\text{ m} < \lambda < 10^{-8}\text{ m}$):** Producidos por el frenado abrupto de electrones de alta energía contra blancos metálicos. Tienen carácter ionizante.
7. **Rayos Gamma ($\lambda < 10^{-10}\text{ m}$, $f > 10^{19}\text{ Hz}$):** Emitidos por reacciones nucleares y desintegración radiactiva. Radiación sumamente penetrante e ionizante.

## 6. Energía Transportada y Vector de Poynting
Los campos eléctrico y magnético almacenan energía en el espacio.

### Densidades Instantáneas de Energía
* **Densidad de Energía Eléctrica:**
  $$u_E = \frac{1}{2} \epsilon_0 E^2$$
* **Densidad de Energía Magnética:**
  $$u_B = \frac{B^2}{2 \mu_0}$$
* **Densidad Total de Energía ($u$):**
  Dado que $B = \frac{E}{c} = \sqrt{\epsilon_0 \mu_0} E$, ambas contribuciones son idénticas ($u_E = u_B$):
  $$u = u_E + u_B = \epsilon_0 E^2 = \frac{B^2}{\mu_0} = \sqrt{\frac{\epsilon_0}{\mu_0}} E B$$

### Vector de Poynting ($\vec{S}$)
El **Vector de Poynting** representa la tasa instantánea de flujo de energía por unidad de área (o potencia por unidad de área) transportada por la onda:
$$\vec{S} = \frac{1}{\mu_0} \vec{E} \times \vec{B} = c^2 \epsilon_0 \vec{E} \times \vec{B} \quad [\text{W/m}^2]$$

#### Magnitud Instantánea del Vector de Poynting
$$S = \frac{E B}{\mu_0} = \frac{E^2}{\mu_0 c} = \frac{c B^2}{\mu_0} = \epsilon_0 c E^2$$

### Intensidad de la Radiación ($I$)
La **intensidad** es el promedio temporal del módulo del Vector de Poynting ($I = \bar{S} = S_{\text{prom}}$). Para ondas sinusoidales, como el valor promedio de $\cos^2(\theta)$ es $\frac{1}{2}$:
$$I = \frac{E_{\text{máx}} B_{\text{máx}}}{2 \mu_0} = \frac{E_{\text{máx}}^2}{2 \mu_0 c} = \frac{c B_{\text{máx}}^2}{2 \mu_0} = \frac{1}{2} \epsilon_0 c E_{\text{máx}}^2$$

## 7. Cantidad de Movimiento y Presión de Radiación
Las ondas electromagnéticas transportan cantidad de movimiento $p$, la cual es transferida a cualquier superficie con la que interactúen.

* **Densidad de Cantidad de Movimiento del Campo:**
  $$\frac{dp}{dV} = \frac{S}{c^2}$$
* **Flujo de Cantidad de Movimiento por Unidad de Área y Tiempo:**
  $$\frac{1}{A} \frac{dp}{dt} = \frac{S}{c}$$

### Presión de Radiación ($p_{\text{rad}}$)
Al transferir cantidad de movimiento, la onda ejerce una fuerza perpendicular sobre la superficie objetivo:
1. **Superficie Totalmente Absorbente:** Toda la energía y momento son absorbidos.
   $$p_{\text{rad}} = \frac{S_{\text{prom}}}{c} = \frac{I}{c} \quad [\text{Pa} \text{ o } \text{N/m}^2]$$
2. **Superficie Totalmente Reflectante:** La onda rebotante invierte su cantidad de movimiento, duplicando la transferencia neta de momento:
   $$p_{\text{rad}} = \frac{2 S_{\text{prom}}}{c} = \frac{2I}{c} \quad [\text{Pa} \text{ o } \text{N/m}^2]$$

## 8. Casos Especiales y Formulaciones Específicas de Ejercicios
1. **Reglas para Escribir Ecuaciones Vectoriales de $\vec{E}$ y $\vec{B}$:**
   * La dirección de propagación $\hat{u}_{\text{prop}}$ debe cumplir:
     $$\hat{u}_E \times \hat{u}_B = \hat{u}_{\text{prop}}$$
   * Si una onda viaja en la dirección $-x$ y $\vec{E}$ apunta en $+z$ ($\hat{k}$), entonces $\vec{B}$ debe apuntar en $+y$ ($\hat{j}$), porque $\hat{k} \times \hat{j} = -\hat{i}$.
2. **Emisión Isotrópica / Hemisférica sobre el Suelo:**
   * Si una fuente puntual sobre el suelo emite una potencia promedio $P$ por igual en todas las direcciones sobre el suelo (superficie hemisférica de área $A = 2\pi r^2$):
     $$I = \frac{P}{2\pi r^2}$$
   * Con la intensidad calculada, se despejan los campos máximos: $E_{\text{máx}} = \sqrt{2 \mu_0 c I}$ y $B_{\text{máx}} = \frac{E_{\text{máx}}}{c}$.
3. **Torque y Aceleración Angular por Presión de Radiación:**
   * En un sistema giratorio con un brazo de longitud $L$ sujeto a luz uniforme:
     * Lado absorbente: $F_{\text{abs}} = p_{\text{abs}} A_{\text{placa}} = \left(\frac{I}{c}\right) A_{\text{placa}}$
     * Lado reflectante: $F_{\text{ref}} = p_{\text{ref}} A_{\text{placa}} = \left(\frac{2I}{c}\right) A_{\text{placa}}$
     * Fuerza neta diferencial: $\Delta F = F_{\text{ref}} - F_{\text{abs}} = \frac{I A_{\text{placa}}}{c}$
     * Torque neto: $\tau = \Delta F \cdot \left(\frac{L}{2}\right)$
     * Aceleración angular: $\alpha = \frac{\tau}{I_{\text{rotacional}}}$

## 9. Formulario Completo Explicado

| Concepto / Nombre de Ecuación | Fórmula | Explicación |
| --- | --- | --- |
| **Ley de Gauss Eléctrica** | $\oint \vec{E} \cdot d\vec{A} = \frac{Q_{\text{enc}}}{\epsilon_0}$ | Relaciona el flujo eléctrico encerrado con la carga neta interna. |
| **Ley de Gauss Magnética** | $\oint \vec{B} \cdot d\vec{A} = 0$ | Indica la inexistencia de monopolos magnéticos aislados. |
| **Ley de Ampère-Maxwell** | $\oint \vec{B} \cdot d\vec{l} = \mu_0 \left( i_c + \epsilon_0 \frac{d\Phi_E}{dt} \right)$ | El campo magnético es generado por corrientes y por cambios en el flujo eléctrico. |
| **Ley de Faraday** | $\oint \vec{E} \cdot d\vec{l} = -\frac{d\Phi_B}{dt}$ | La variación del flujo magnético induce un campo eléctrico. |
| **Ecuación de Onda Diferencial ($E$)** | $\frac{\partial^2 E_y}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 E_y}{\partial t^2}$ | Ecuación diferencial de propagación para la componente del campo eléctrico. |
| **Ecuación de Onda Diferencial ($B$)** | $\frac{\partial^2 B_z}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 B_z}{\partial t^2}$ | Ecuación diferencial de propagación para la componente del campo magnético. |
| **Rapidez de la Luz en el Vacío** | $c = \frac{1}{\sqrt{\epsilon_0 \mu_0}} \approx 3.00 \times 10^8\text{ m/s}$ | Velocidad constante e invariable de las ondas EM en el vacío. |
| **Relación de Magnitudes Instantáneas** | $E = c B \quad \implies \quad E_{\text{máx}} = c B_{\text{máx}}$ | Proporción estricta entre las amplitudes y valores instantáneos de $\vec{E}$ y $\vec{B}$. |
| **Onda Senoidal de Campo Eléctrico** | $\vec{E}(x,t) = \hat{j} E_{\text{máx}} \cos(kx \mp \omega t)$ | Función de onda armónica para un campo eléctrico linealmente polarizado. |
| **Onda Senoidal de Campo Magnético** | $\vec{B}(x,t) = \hat{k} B_{\text{máx}} \cos(kx \mp \omega t)$ | Función de onda armónica para el campo magnético acoplado en fase. |
| **Rapidez de Onda en la Materia** | $v = \frac{1}{\sqrt{\epsilon \mu}} = \frac{c}{\sqrt{K K_m}}$ | Velocidad de propagación de la onda EM dentro de un medio dieléctrico. |
| **Índice de Refracción** | $n = \frac{c}{v} = \sqrt{K K_m} \approx \sqrt{K}$ | Razón de desaceleración de la luz en un medio transparente respecto al vacío. |
| **Frecuencia, Longitud de Onda y $c$** | $c = f \cdot \lambda = \frac{\omega}{k}$ | Relación cinemática entre la velocidad de la luz, frecuencia y longitud de onda. |
| **Densidad Total de Energía ($u$)** | $u = \epsilon_0 E^2 = \frac{B^2}{\mu_0}$ | Energía por unidad de volumen almacenada en las regiones con campos EM. |
| **Vector de Poynting** | $\vec{S} = \frac{1}{\mu_0} \vec{E} \times \vec{B}$ | Vector que indica la dirección y magnitud del flujo de energía instantáneo por área. |
| **Módulo Instantáneo de Poynting** | $S = \frac{E B}{\mu_0} = \frac{E^2}{\mu_0 c} = \epsilon_0 c E^2$ | Tasa instantánea de transferencia de energía por unidad de superficie ($\text{W/m}^2$). |
| **Intensidad de Radiación ($I$)** | $I = S_{\text{prom}} = \frac{E_{\text{máx}} B_{\text{máx}}}{2 \mu_0} = \frac{1}{2} \epsilon_0 c E_{\text{máx}}^2$ | Valor medio del Vector de Poynting transportado por una onda senoidal. |
| **Presión de Radiación (Absorción)** | $p_{\text{rad}} = \frac{I}{c}$ | Presión ejercida por una onda sobre una superficie perfectamente absorbente. |
| **Presión de Radiación (Reflexión)** | $p_{\text{rad}} = \frac{2I}{c}$ | Presión ejercida por una onda sobre una superficie perfectamente reflejante. |
| **Fuerza por Presión de Radiación** | $F = p_{\text{rad}} \cdot A$ | Fuerza ejercida por el impacto continuo de la radiación sobre el área $A$. |
