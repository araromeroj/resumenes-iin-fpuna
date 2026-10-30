# Resumen Completo de Física III: Ondas Sonoras

## 1. Naturaleza y Clasificación de las Ondas Sonoras
Las ondas sonoras son ondas mecánicas longitudinales que consisten en perturbaciones de la presión y del desplazamiento que se propagan a través de un medio material (sólido, líquido o gas).

### Clasificación según la Frecuencia
1. **Ondas Audibles:** Frecuencias dentro del intervalo de detección del oído humano promedio:
   $$20\text{ Hz} \le f \le 20\,000\text{ Hz}$$
2. **Ondas Infrasónicas:** Frecuencias por debajo del límite audible inferior:
   $$f < 20\text{ Hz}$$
3. **Ondas Ultrasónicas:** Frecuencias por encima del límite audible superior:
   $$f > 20\,000\text{ Hz}$$

## 2. Descripción Matemática: Ondas de Desplazamiento y de Presión
Cuando una onda sonora periódica viaja a lo largo de un medio (por ejemplo, dentro de un tubo con un pistón oscilante), genera regiones alternadas de alta densidad y presión (compresiones) y de baja densidad y presión (enrarecimientos o rarefacciones).

### Función de Onda de Desplazamiento
Representa la posición de los elementos de masa del medio respecto a su posición de equilibrio $x$:
$$s(x,t) = s_{\text{máx}} \cos(kx - \omega t) \quad \text{o} \quad s(x,t) = s_{\text{máx}} \sin(kx - \omega t - \phi)$$

Donde:
- $s_{\text{máx}}$: Amplitud de desplazamiento de las partículas del medio.
- $k = \frac{2\pi}{\lambda}$: Número de onda.
- $\omega = 2\pi f$: Frecuencia angular.

### Función de Onda de Fluctuación de Presión
La variación de presión $\Delta p(x,t) = p(x,t) - p_0$ respecto a la presión de equilibrio $p_0$ viene dada por:
$$\Delta p(x,t) = \Delta p_{\text{máx}} \sin(kx - \omega t) \quad \text{o} \quad \Delta p(x,t) = \Delta p_{\text{máx}} \cos(kx - \omega t - \phi)$$

### Amplitud de Presión y Relación de Desfase
La amplitud máxima de fluctuación de presión $\Delta p_{\text{máx}}$ está ligada a las propiedades del medio y a la amplitud de desplazamiento:
$$\Delta p_{\text{máx}} = \rho v \omega s_{\text{máx}} = B k s_{\text{máx}}$$

- **Desfase:** Las ondas de desplazamiento y de presión están desfasadas en $\frac{\pi}{2}\text{ rad}$ ($90^\circ$). Cuando el desplazamiento de las partículas es nulo ($s = 0$), el cambio de presión es máximo ($\Delta p = \pm \Delta p_{\text{máx}}$) y viceversa.

## 3. Rapidez de Propagación del Sonido
La rapidez del sonido responde a la estructura general de las ondas mecánicas:
$$v = \sqrt{\frac{\text{Propiedad Elástica}}{\text{Propiedad Inercial}}}$$

### Rapidez en Diferentes Medios
1. **Barras o Varillas Sólidas:**
   $$v = \sqrt{\frac{Y}{\rho}}$$
   Donde $Y$ es el módulo de Young y $\rho$ es la densidad volumétrica del sólido.
2. **Fluidos (Líquidos y Gases en General):**
   $$v = \sqrt{\frac{B}{\rho}}$$
   Donde $B$ (o $K$) es el módulo de compresibilidad volumétrico del fluido.
3. **Gases Ideales:**
   $$v = \sqrt{\frac{\gamma R T}{M}}$$
   Donde:
   - $\gamma$: Coeficiente adiabático del gas ($\gamma \approx 1.67$ monoatómico, $1.40$ diatómico, $1.33$ poliatómico).
   - $R = 8.314\text{ J/(mol}\cdot\text{K)}$: Constante universal de los gases.
   - $T$: Temperatura absoluta en Kelvin ($\text{K}$).
   - $M$: Masa molar del gas en $\text{kg/mol}$.
4. **Sonido en el Aire en Función de la Temperatura en Celsius:**
   $$v = 331 \sqrt{1 + \frac{T_C}{273}} \quad [\text{m/s}]$$
   Donde $T_C$ es la temperatura del aire en grados Celsius ($^\circ\text{C}$).

## 4. Intensidad de las Ondas Sonoras
La intensidad ($I$) es la rapidez media con la que una onda transporta energía por unidad de área perpendicular a la dirección de propagación:
$$I = \frac{P}{A} = \frac{\Delta E}{\Delta t \, \Delta A}$$

### Expresiones de Intensidad
En función de la amplitud de desplazamiento $s_{\text{máx}}$ o de la amplitud de presión $\Delta p_{\text{máx}}$:
$$I = \frac{1}{2} \rho v \omega^2 s_{\text{máx}}^2 = \frac{(\Delta p_{\text{máx}})^2}{2 \rho v}$$

### Ondas Esféricas (Fuente Puntual Isotrópica)
Si una fuente puntual emite una potencia promedio $P_{\text{prom}}$ uniformemente en todas las direcciones (tres dimensiones):
$$I = \frac{P_{\text{prom}}}{4\pi r^2} \implies I \propto \frac{1}{r^2}$$

## 5. Nivel Sonoro ($\beta$) y Decibeles
Dado que el oído humano percibe intensidades en un rango sumamente amplio (desde $10^{-12}\text{ W/m}^2$ hasta más de $1\text{ W/m}^2$), se define la escala logarítmica del Nivel Sonoro ($\beta$):
$$\beta = 10 \log_{10}\left(\frac{I}{I_0}\right) \quad [\text{dB}]$$

### Valores de Referencia
- **Umbral de Audición ($I_0$):** Intensidad mínima perceptible a $1000\text{ Hz}$:
  $$I_0 = 10^{-12}\text{ W/m}^2 \quad (\beta = 0\text{ dB})$$
- **Umbral del Dolor:**
  $$I \approx 1\text{ W/m}^2 \quad (\beta = 120\text{ dB})$$

### Propiedades y Relaciones Útiles
1. **Diferencia de Niveles Sonoros en Función de la Distancia:**
   Para una fuente puntual esférica sin absorción:
   $$\beta_2 - \beta_1 = 10 \log_{10}\left(\frac{I_2}{I_1}\right) = 10 \log_{10}\left(\frac{r_1^2}{r_2^2}\right) = 20 \log_{10}\left(\frac{r_1}{r_2}\right)$$
2. **Superposición de Fuentes Incoherentes:**
   Las intensidades se suman directamente, no los niveles en decibeles:
   $$I_{\text{total}} = \sum I_i \implies \beta_{\text{total}} = 10 \log_{10}\left(\frac{\sum I_i}{I_0}\right)$$
3. **Atenuación del Medio:**
   Si el medio absorbe energía sonora a una tasa de $\alpha\text{ [dB/Km]}$ , el nivel sonoro a una distancia $r$ disminuye según:
   $$\beta(r) = \beta_{\text{sin atenuación}}(r) - \alpha \cdot r$$

## 6. Efecto Doppler
El Efecto Doppler es el cambio aparente en la frecuencia de una onda percibida por un observador debido al movimiento relativo entre la fuente de sonido y dicho observador.

### Variables
- $v$: Rapidez del sonido en el medio.
- $v_O$: Rapidez del observador.
- $v_F$: Rapidez de la fuente.
- $f$: Frecuencia emitida por la fuente.
- $f'$: Frecuencia percibida por el observador.

### Análisis por Casos
- **Caso 1: Observador en Movimiento, Fuente en Reposo ($v_F = 0$)**
  El observador percibe una rapidez relativa del sonido $v' = v \pm v_O$, manteniendo la misma longitud de onda $\lambda$:
  $$f' = f \left(\frac{v \pm v_O}{v}\right)$$
  - $+$ si el observador se acerca a la fuente (aumenta $f'$).
  - $-$ si el observador se aleja de la fuente (disminuye $f'$).

- **Caso 2: Fuente en Movimiento, Observador en Reposo ($v_O = 0$)**
  El movimiento de la fuente comprime o expande la longitud de onda en el medio ($\lambda' = \lambda \mp \Delta \lambda = \frac{v \mp v_F}{f}$):
  $$f' = f \left(\frac{v}{v \mp v_F}\right)$$
  - $-$ si la fuente se acerca al observador (aumenta $f'$).
  - $+$ si la fuente se aleja del observador (disminuye $f'$).

- **Caso 3: Fuente y Observador en Movimiento Simultáneo (Ecuación General)**
  $$f' = f \left(\frac{v + v_O}{v - v_F}\right)$$

### Convención Universal de Signos
- $v_O$ es positiva si el observador se mueve hacia la fuente; negativa si se aleja.
- $v_F$ es positiva si la fuente se mueve hacia el observador; negativa si se aleja.

### Casos Especiales de Ejercicios Prácticos
1. **Reflexión de Onda / Eco (Murciélago o Radar/Sonar):**
   - *Etapa 1:* El objeto reflector actúa como observador móvil y percibe una frecuencia $f'$.
   - *Etapa 2:* El objeto reflector actúa inmediatamente como una fuente móvil que emite $f'$ de regreso hacia el emisor original.
2. **Fuente Unida a un Oscilador Armónico Simple (M.A.S.):**
   - La rapidez de la fuente es variable: $v_F(t) = v_{\text{máx}} \cos(\omega_{\text{MAS}} t)$, con $v_{\text{máx}} = \omega_{\text{MAS}} A = \sqrt{\frac{k}{m}} A$.
   - La frecuencia percibida máxima $f_{\text{máx}}'$ ocurre cuando la fuente pasa por la posición de equilibrio acercándose al observador.
   - La frecuencia percibida mínima $f_{\text{mín}}'$ ocurre cuando la fuente pasa por la posición de equilibrio alejándose del observador.
3. **Fuente en Caída Libre:**
   - La rapidez de la fuente en función de la altura $h$ recorrida es $v_F = \sqrt{2 g h}$.

## 7. Formulario Completo Explicado

| Concepto / Nombre de Ecuación | Fórmula | Explicación |
| :--- | :--- | :--- |
| **Función de Desplazamiento** | $s(x,t) = s_{\text{máx}} \cos(kx - \omega t)$ | Describe la posición oscilatoria de las partículas del medio respecto al equilibrio. |
| **Función de Presión** | $\Delta p(x,t) = \Delta p_{\text{máx}} \sin(kx - \omega t)$ | Describe la fluctuación de presión en el medio, desfasada $\pi/2\text{ rad}$ respecto al desplazamiento. |
| **Amplitud de Presión** | $\Delta p_{\text{máx}} = \rho v \omega s_{\text{máx}} = B k s_{\text{máx}}$ | Relación entre la amplitud de fluctuación de presión y la amplitud de desplazamiento $s_{\text{máx}}$. |
| **Rapidez del Sonido en Sólidos** | $v = \sqrt{\frac{Y}{\rho}}$ | Rapidez en una barra sólida en función del Módulo de Young $Y$ y la densidad $\rho$. |
| **Rapidez del Sonido en Fluidos** | $v = \sqrt{\frac{B}{\rho}}$ | Rapidez en líquidos/gases según el Módulo de Compresibilidad Volumétrico $B$. |
| **Rapidez del Sonido en Gases Ideales** | $v = \sqrt{\frac{\gamma R T}{M}}$ | Rapidez en función de la temperatura absoluta $T$, masa molar $M$ y coeficiente adiabático $\gamma$. |
| **Rapidez en Aire vs Temperatura** | $v = 331 \sqrt{1 + \frac{T_C}{273}}$ | Rapidez del sonido en el aire según la temperatura $T_C$ en grados Celsius. |
| **Intensidad de Onda Sonora** | $I = \frac{1}{2} \rho v \omega^2 s_{\text{máx}}^2 = \frac{(\Delta p_{\text{máx}})^2}{2 \rho v}$ | Energía media transportada por unidad de área y tiempo ($\text{W/m}^2$). |
| **Intensidad de Onda Esférica** | $I = \frac{P_{\text{prom}}}{4 \pi r^2}$ | Intensidad distribuida sobre una superficie esférica de radio $r$ para una fuente puntual. |
| **Nivel Sonoro (Decibeles)** | $\beta = 10 \log_{10}\left(\frac{I}{I_0}\right)$ | Medida logarítmica de la intensidad relativa respecto al umbral $I_0 = 10^{-12}\text{ W/m}^2$. |
| **Diferencia de Niveles Sonoros** | $\beta_2 - \beta_1 = 20 \log_{10}\left(\frac{r_1}{r_2}\right)$ | Variación del nivel sonoro entre dos puntos a distancias $r_1$ y $r_2$ de una fuente puntual. |
| **Atenuación por el Medio** | $\beta(r) = \beta_{\text{teórico}}(r) - \alpha \cdot r$ | Corrección del nivel sonoro debido a la absorción de energía por el medio ($\alpha$ en $\text{dB/km}$). |
| **Efecto Doppler (Observador Móvil)** | $f' = f \left(\frac{v \pm v_O}{v}\right)$ | Cambio de frecuencia debido al movimiento del observador con rapidez $v_O$. |
| **Efecto Doppler (Fuente Móvil)** | $f' = f \left(\frac{v}{v \mp v_F}\right)$ | Cambio de frecuencia debido al movimiento de la fuente con rapidez $v_F$. |
| **Efecto Doppler General** | $f' = f \left(\frac{v + v_O}{v - v_F}\right)$ | Expresión general cuando observador y fuente están en movimiento simultáneo. |
| **Longitud de Onda Modificada (Doppler)** | $\lambda' = \frac{v \mp v_F}{f}$ | Longitud de onda en el medio por delante o por detrás de una fuente en movimiento. |
| **Efecto Doppler con M.A.S.** | $v_{F,\text{máx}} = \omega_{\text{MAS}} A = \sqrt{\frac{k}{m}} A$ | Rapidez máxima de una fuente oscilante que genera las frecuencias extremas $f_{\text{máx}}'$ y $f_{\text{mín}}'$. |