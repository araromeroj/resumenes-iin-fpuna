## 1. Naturaleza y Caracterización de las Ondas Sonoras
* **Definición y Origen:** Las ondas sonoras son ondas mecánicas longitudinales que consisten en perturbaciones o fluctuaciones periódicas de la presión y la densidad de un medio material (gas, líquido o sólido). Se propagan en forma de zonas alternadas de **compresión** (alta densidad y presión) y **enrarecimiento o rarefacción** (baja densidad y presión).
* **Doble Naturaleza (Desplazamiento vs. Presión):**
  * *Onda de Desplazamiento $s(x,t)$:* Describe las oscilaciones longitudinales de las partículas del medio alrededor de sus posiciones de equilibrio.
  * *Onda de Presión $\Delta p(x,t)$:* Describe las desviaciones de la presión respecto al valor de equilibrio no perturbado.
  * *Relación de Fase:* Presentan un desfase fundamental de $\pi/2$ rad ($90^\circ$). Cuando el desplazamiento de las partículas es máximo, la variación de presión es nula; y cuando la variación de presión alcanza un máximo o mínimo (compresión/rarefacción), el desplazamiento es cero.
* **Clasificación Espectral por Audición Humana:**
  * *Audibles:* Frecuencias comprendidas en el rango de percepción del oído humano (aproximadamente entre $20\text{ Hz}$ y $20\,000\text{ Hz}$).
  * *Infrasónicas:* Frecuencias por debajo del límite audible inferior ($< 20\text{ Hz}$).
  * *Ultrasónicas:* Frecuencias por encima del límite audible superior ($> 20\,000\text{ Hz}$).
---
## 2. Propagación y Rapidez del Sonido en Diversos Medios
* **Principio General:** La rapidez de propagación depende de las propiedades elásticas (fuerza restauradora) e inerciales (densidad) del medio material:
  $$v = \sqrt{\frac{\text{propiedad elástica}}{\text{propiedad inercial}}}$$
* **Sólidos (Barras o Varillas):** 
  $$v = \sqrt{\frac{Y}{\rho}}$$
  donde $Y$ es el Módulo de Young y $\rho$ es la densidad de masa.
* **Líquidos y Fluidos Generales:** 
  $$v = \sqrt{\frac{K}{\rho}} \quad \text{o} \quad v = \sqrt{\frac{B}{\rho}}$$
  donde $K$ (o $B$) es el módulo de compresibilidad o volumétrico.
* **Gases Ideales:** 
  $$v = \sqrt{\frac{\gamma R T}{M}}$$
  donde $\gamma$ es el coeficiente adiabático del gas ($1{,}67$ monoatómico; $1{,}4$ diatómico; $1{,}3$ poliatómico), $R$ es la constante universal ($8{,}314\text{ J/mol}\cdot\text{K}$), $T$ es la temperatura absoluta en Kelvin y $M$ es la masa molar.
* **Aproximación en Aire según Temperatura ($T$ en $^\circ\text{C}$):** 
  $$v = 331 \sqrt{1 + \frac{T}{273}} \text{ m/s}$$
---
## 3. Energía, Intensidad y Nivel Sonoro ($\beta$)
* **Intensidad Sonora ($I$):** Rapidez con la que se transporta energía por unidad de área perpendicular a la dirección de propagación:
  $$I = \frac{P}{A} \quad [\text{W/m}^2]$$
* **Ondas Esféricas (Fuente Puntual e Isótropa):** Sigue la ley del inverso del cuadrado de la distancia:
  $$I = \frac{P_{\text{prom}}}{4 \pi r^2} \implies I \propto \frac{1}{r^2}$$
* **Nivel Sonoro ($\beta$ en dB):** Escala logarítmica para abarcar el amplio rango audible:
  $$\beta = 10 \log_{10} \left( \frac{I}{I_0} \right)$$
  donde $I_0 = 10^{-12}\text{ W/m}^2$ es el umbral de audición de referencia a $1000\text{ Hz}$.
* **Relación de Niveles por Distancia:**
  $$\beta_2 - \beta_1 = 20 \log_{10} \left( \frac{r_1}{r_2} \right)$$
---
## 4. Efecto Doppler
* **Fenómeno:** Cambio en la frecuencia percibida ($f'$) respecto a la frecuencia emitida ($f$) debido al movimiento relativo entre la fuente y el observador.
* **Convenio de Signos Estándar:**
  * *Velocidad del Observador ($v_O$):* Positiva ($+$) cuando se mueve **hacia** la fuente (acercamiento) y negativa ($-$) cuando se aleja.
  * *Velocidad de la Fuente ($v_F$):* Positiva ($+$) cuando se mueve **hacia** el observador (acercamiento) y negativa ($-$) cuando se aleja.
* **Formulación General:**
  $$f' = f \left( \frac{v + v_O}{v - v_F} \right)$$
  donde $v$ es la rapidez del sonido en el medio.
---
## 5. Formulario Completo Explicado

| Concepto / Nombre de Ecuación | Fórmula | Explicación |
| :--- | :--- | :--- |
| **Onda de Desplazamiento** | $s(x,t) = s_{\max} \cos(kx - \omega t - \phi)$ | Describe la posición longitudinal de las partículas del medio respecto al equilibrio. $s_{\max}$ es la amplitud. |
| **Onda de Presión** | $\Delta p(x,t) = \Delta p_{\max} \sin(kx - \omega t - \phi)$ | Describe la fluctuación local de presión. Desfasada $\pi/2\text{ rad}$ con la onda de desplazamiento. |
| **Amplitud de Presión** | $\Delta p_{\max} = \rho v \omega s_{\max}$ | Relaciona la amplitud máxima de presión con la densidad $\rho$, velocidad $v$, frecuencia angular $\omega$ y amplitud $s_{\max}$. |
| **Rapidez del Sonido en Sólidos** | $v = \sqrt{\frac{Y}{\rho}}$ | Velocidad del sonido en una barra sólida según el Módulo de Young $Y$ y densidad $\rho$. |
| **Rapidez del Sonido en Fluidos** | $v = \sqrt{\frac{K}{\rho}}$ o $\sqrt{\frac{B}{\rho}}$ | Velocidad en líquidos o gases según el módulo volumétrico $K$ (o $B$) y la densidad $\rho$. |
| **Rapidez en Gases Ideales** | $v = \sqrt{\frac{\gamma R T}{M}}$ | Velocidad en gases ideales según constante adiabática $\gamma$, constante $R$, temperatura $T$ y masa molar $M$. |
| **Rapidez en Aire seg. Temperatura** | $v = 331 \sqrt{1 + \frac{T}{273}}$ | Aproximación empírica para la velocidad del sonido en aire a temperatura $T$ en $^\circ\text{C}$ (m/s). |
| **Intensidad Sonora (General)** | $I = \frac{1}{2} \rho v \omega^2 s_{\max}^2 = \frac{(\Delta p_{\max})^2}{2 \rho v}$ | Transporte promedio de energía por unidad de área ($\text{W/m}^2$) en función de desplazamiento o presión. |
| **Intensidad en Ondas Esféricas** | $I = \frac{P_{\text{prom}}}{4 \pi r^2}$ | Intensidad emitida por fuente puntual a una distancia $r$. Sigue la ley $I \propto 1/r^2$. |
| **Nivel Sonoro ($\beta$)** | $\beta = 10 \log_{10} \left( \frac{I}{I_0} \right)$ | Medida en decibeles (dB). $I_0 = 10^{-12}\text{ W/m}^2$ (umbral de audición de referencia). |
| **Diferencia de Niveles por Distancia** | $\beta_2 - \beta_1 = 20 \log_{10} \left( \frac{r_1}{r_2} \right)$ | Variación del nivel sonoro en decibeles entre dos puntos a distancias $r_1$ y $r_2$ de la fuente. |
| **Doppler: Observador en Movimiento** | $f' = f \left( \frac{v \pm v_O}{v} \right)$ | Fuente en reposo, observador moviéndose a $v_O$ ($+$ si se acerca, $-$ si se aleja). |
| **Doppler: Fuente en Movimiento** | $f' = f \left( \frac{v}{v \mp v_F} \right)$ | Observador en reposo, fuente moviéndose a $v_F$ ($-$ si se acerca, $+$ si se aleja). |
| **Efecto Doppler General** | $f' = f \left( \frac{v + v_O}{v - v_F} \right)$ | Movimiento simultáneo. $v_O > 0$ si el observador se acerca a la fuente; $v_F > 0$ si la fuente se acerca al observador. |