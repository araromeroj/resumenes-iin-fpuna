# 📐 Formulario de Física III: Oscilaciones, Ondas y Electromagnetismo

> [!info] **Descripción General del Documento**
> Este formulario interactivo para **Obsidian** reúne y clasifica las 57 fórmulas esenciales del curso de **Física III** (Oscilaciones Libres y Amortiguadas, Resonancia, Ondas Mecánicas, Acústica, Interferencia, Electromagnetismo y Presión de Radiación). Cada fórmula incluye su número original, expresión matemática en LaTeX, nombre formal, desglose de variables y la descripción conceptual del movimiento o situación física en la que se aplica.

---

## 📑 Tabla de Contenidos

1. 1. Movimiento Armónico Simple (MAS) Libre
2. 2. Oscilaciones Amortiguadas
3. 3. Oscilaciones Forzadas y Resonancia
4. 4. Movimiento Ondulatorio y Ondas Mecánicas
5. 5. Acústica, Intensidad Sonora y Efecto Doppler
6. 6. Interferencia, Superposición y Ondas Estacionarias
7. 7. Ondas Electromagnéticas y Vector de Poynting
8. 8. Momento, Presión de Radiación e Inercia
9. 9. Apéndice Matemático

---

## 1. Movimiento Armónico Simple (MAS) Libre

> [!note] **Contexto Físico**
> Movimiento periódico de un cuerpo alrededor de una posición de equilibrio bajo la acción de una fuerza restauradora lineal ($F = -kx$). Se asume un sistema ideal libre de disipación o fricción.

### (1) Ecuación de Posición / Desplazamiento del MAS
* **Fórmula:**
  $$x(t) = A \sin(\omega t +  lpha)$$
* **Nombre:** Ecuación temporal de posición del Movimiento Armónico Simple.
* **Situación y Uso:** Se utiliza para determinar la posición $x$ de una partícula oscilante en cualquier instante de tiempo $t$.
* **Variables:**
  * $x(t)$: Posición o elongación respecto al equilibrio $[\text{m}]$.
  * $A$: Amplitud máxima del movimiento $[\text{m}]$.
  * $\omega$: Frecuencia angular natural $[\text{rad/s}]$.
  * $t$: Tiempo $[\text{s}]$.
  * $\alpha$: Fase inicial o ángulo de desfase en $t=0$ $[\text{rad}]$.

---

### (2) Frecuencia Angular en función del Período
* **Fórmula:**
  $$\omega = \frac{2\pi}{T}$$
* **Nombre:** Relación entre frecuencia angular y período.
* **Situación y Uso:** Permite calcular la velocidad angular/frecuencia angular $\omega$ conociendo la duración $T$ de un ciclo completo.
* **Variables:**
  * $\omega$: Frecuencia angular $[\text{rad/s}]$.
  * $T$: Período de oscilación $[\text{s}]$.

---

### (3) Relación entre Período y Frecuencia Temporal
* **Fórmula:**
  $$T = \frac{1}{f}$$
* **Nombre:** Relación recíproca entre período y frecuencia.
* **Situación y Uso:** Se emplea para convertir entre el tiempo invertido en un ciclo ($T$) y la cantidad de ciclos por unidad de tiempo ($f$).
* **Variables:**
  * $T$: Período $[\text{s}]$.
  * $f$: Frecuencia $[\text{Hz} = \text{s}^{-1}]$.

---

### (4) Frecuencia Angular del Sistema Masa-Resorte
* **Fórmula:**
  $$\omega = \sqrt{\frac{k}{m}}$$
* **Nombre:** Frecuencia angular natural del oscilador masa-resorte.
* **Situación y Uso:** Calcula la rapidez con la que oscila libremente un bloque de masa $m$ unido a un resorte ideal de constante elástica $k$.
* **Variables:**
  * $\omega$: Frecuencia angular natural $[\text{rad/s}]$.
  * $k$: Constante elástica del resorte $[\text{N/m}]$.
  * $m$: Masa del oscilador $[\text{kg}]$.

---

### (5) Energía Cinética del MAS en función del Tiempo
* **Fórmula:**
  $$K = \frac{1}{2}m v^2 = \frac{1}{2}m\omega^2 A^2 \cos^2(\omega t + \alpha)$$
* **Nombre:** Ecuación de energía cinética del MAS en el dominio del tiempo.
* **Situación y Uso:** Describe la variación temporal de la energía cinética del oscilador. Muestra que la energía cinética oscila al doble de la frecuencia del movimiento entre $0$ y $K_{	ext{máx}}$.
* **Variables:**
  * $K$: Energía cinética instantánea $[\text{J}]$.
  * $v$: Velocidad instantánea $[\text{m/s}]$.
  * $m$: Masa del cuerpo $[\text{kg}]$.
  * $A$: Amplitud $[\text{m}]$.

---

### (6) Energía Cinética del MAS en función de la Posición
* **Fórmula:**
  $$K = \frac{1}{2}m\omega^2 (A^2 - x^2)$$
* **Nombre:** Energía cinética del MAS respecto a la elongación.
* **Situación y Uso:** Permite hallar la energía cinética o la velocidad del oscilador en un punto específico $x$ de la trayectoria sin conocer el tiempo.
* **Variables:**
  * $K$: Energía cinética $[\text{J}]$.
  * $x$: Posición o elongación $[\text{m}]$.
  * $A$: Amplitud $[\text{m}]$.

---

### (7) Energía Potencial Elástica del MAS
* **Fórmula:**
  $$U = \frac{1}{2}k x^2 = \frac{1}{2}m\omega^2 x^2$$
* **Nombre:** Energía potencial elástica instantánea.
* **Situación y Uso:** Evalúa la energía almacenada en el resorte o sistema restaurador cuando la partícula se encuentra desplazada una distancia $x$ de la posición de equilibrio.
* **Variables:**
  * $U$: Energía potencial elástica $[\text{J}]$.
  * $k$: Constante de restitución $[\text{N/m}]$.
  * $x$: Posición respecto al origen $[\text{m}]$.

---

### (8) Amplitud a partir de las Condiciones Iniciales
* **Fórmula:**
  $$A = \sqrt{x_0^2 + \left(\frac{v_0}{\omega}\right)^2}$$
* **Nombre:** Expresión de la amplitud mediante condiciones iniciales.
* **Situación y Uso:** Determina la amplitud total de la oscilación conociendo la posición inicial $x_0$ y la velocidad inicial $v_0$ en el instante $t = 0$.
* **Variables:**
  * $A$: Amplitud resultante $[\text{m}]$.
  * $x_0$: Posición inicial en $t=0$ $[\text{m}]$.
  * $v_0$: Velocidad inicial en $t=0$ $[\text{m/s}]$.

---

### (9) Ecuación Diferencial del MAS libre
* **Fórmula:**
  $$\frac{d^2x}{dt^2} + \omega^2 x = 0$$
* **Nombre:** Ecuación diferencial del oscilador armónico simple.
* **Situación y Uso:** Ecuación fundamental que rige a todo sistema dinámico conservativo que realiza un movimiento armónico simple en ausencia de fuerzas disipativas.
* **Variables:**
  * $\frac{d^2x}{dt^2}$: Aceleración instantánea $a(t)$ $[\text{m/s}^2]$.
  * $\omega$: Frecuencia angular natural $[\text{rad/s}]$.

---

## 2. Oscilaciones Amortiguadas

> [!warning] **Contexto Físico**
> Ocurre cuando el sistema experimenta fuerzas disipativas (fricción viscosa $F_d = -b v$). La energía mecánica se disipa gradualmente en forma de calor y la amplitud disminuye con el tiempo.

### (10) Coeficiente de Amortiguamiento
* **Fórmula:**
  $$\gamma = \frac{b}{2m}$$
* **Nombre:** Factor / constante de amortiguamiento (o atenuación).
* **Situación y Uso:** Mide la intensidad de la fuerza disipativa por unidad de masa. Define los regímenes de oscilación (subamortiguado, crítico o sobreamortiguado).
* **Variables:**
  * $\gamma$: Factor de amortiguamiento $[\text{s}^{-1}]$.
  * $b$: Coeficiente de fricción viscosa $[\text{kg/s}]$ o $[\text{N}\cdot\text{s/m}]$.
  * $m$: Masa del oscilador $[\text{kg}]$.

---

### (11) Ecuación Diferencial del Oscilador Amortiguado
* **Fórmula:**
  $$\frac{d^2x}{dt^2} + 2\gamma \frac{dx}{dt} + \omega_0^2 x = 0$$
* **Nombre:** Ecuación diferencial del movimiento amortiguado libre.
* **Situación y Uso:** Modela el movimiento de una masa sujeta a una fuerza recuperadora lineal y a una fuerza de resistencia viscosa proporcional a la velocidad.
* **Variables:**
  * $\gamma$: Factor de amortiguamiento $[\text{s}^{-1}]$.
  * $\omega_0$: Frecuencia natural no amortiguada ($\sqrt{k/m}$) $[\text{rad/s}]$.

---

### (12) Solución para el Régimen Sobreamortiguado
* **Fórmula:**
  $$x(t) = A_1 e^{-(\gamma - q)t} + A_2 e^{-(\gamma + q)t} \quad \text{donde} \quad q = \sqrt{\gamma^2 - \omega_0^2}$$
* **Nombre:** Ecuación de posición en régimen sobreamortiguado ($\gamma > \omega_0$).
* **Situación y Uso:** Se usa cuando el rozamiento es muy fuerte. El sistema no realiza oscilaciones; simplemente retorna exponencialmente y de forma lenta a su posición de equilibrio.
* **Variables:**
  * $A_1, A_2$: Constantes determinadas por las condiciones iniciales.
  * $q$: Parámetro característico de sobreamortiguamiento $[\text{s}^{-1}]$.

---

### (13) Solución para el Régimen con Amortiguamiento Crítico
* **Fórmula:**
  $$x(t) = e^{-\gamma t}(A + B t)$$
* **Nombre:** Ecuación de posición en régimen críticamente amortiguado ($\gamma = \omega_0$).
* **Situación y Uso:** Describe el comportamiento donde el sistema regresa a la posición de equilibrio en el **menor tiempo posible** sin oscilar. Muy utilizado en el diseño de amortiguadores de vehículos y amortiguamiento de instrumentos de medición.
* **Variables:**
  * $A, B$: Constantes dependientes de las condiciones iniciales.

---

### (14) Pseudofrecuencia Angular Amortiguada
* **Fórmula:**
  $$\omega_d = \sqrt{\omega_0^2 - \gamma^2}$$
* **Nombre:** Frecuencia angular del movimiento subamortiguado.
* **Situación y Uso:** Calcula la frecuencia de oscilación real en el régimen subamortiguado ($\gamma < \omega_0$). Muestra que la presencia de amortiguamiento disminuye la frecuencia respecto a la natural ($\omega_d < \omega_0$).
* **Variables:**
  * $\omega_d$: Frecuencia angular amortiguada $[\text{rad/s}]$.
  * $\omega_0$: Frecuencia natural no amortiguada $[\text{rad/s}]$.

---

### (15) Solución para el Régimen Subamortiguado
* **Fórmula:**
  $$x(t) = A e^{-\gamma t} \sin(\omega_d t + \phi_0)$$
* **Nombre:** Ecuación de posición para movimiento subamortiguado ($\gamma < \omega_0$).
* **Situación y Uso:** Describe un movimiento oscilatorio de frecuencia $\omega_d$ cuya amplitud decae exponencialmente con el tiempo según la envolvente $A(t) = A e^{-\gamma t}$.
* **Variables:**
  * $A$: Amplitud inicial $[\text{m}]$.
  * $\phi_0$: Fase inicial $[\text{rad}]$.

---

### (16) Tiempo de Relajación o Vida Media de la Energía
* **Fórmula:**
  $$	\tau = \frac{1}{2\gamma}$$
* **Nombre:** Constante de tiempo de relajación de la energía.
* **Situación y Uso:** Representa el intervalo de tiempo necesario para que la energía mecánica total del oscilador amortiguado se reduzca a un factor $1/e\approx 36.8\%$ de su valor inicial.
* **Variables:**
  * $\tau$: Tiempo de relajación $[\text{s}]$.
  * $\gamma$: Factor de amortiguamiento $[\text{s}^{-1}]$.

---

### (17) Decaimiento Exponencial de la Energía Mecánica
* **Fórmula:**
  $$E = \frac{1}{2}m\omega_0^2 A^2 e^{-t/\tau}$$
* **Nombre:** Energía mecánica total en oscilaciones amortiguadas.
* **Situación y Uso:** Muestra la pérdida progresiva e irreversible de energía del oscilador disipada en el medio ambiente en función del tiempo.
* **Variables:**
  * $E$: Energía mecánica instantánea $[\text{J}]$.
  * $\tau$: Tiempo de relajación $[\text{s}]$.

---

### (18) Factor de Calidad (Q)
* **Fórmula:**
  $$Q = 2\pi \frac{E}{|\Delta E|_{	\text{ciclo}}} = \omega_d \tau = \frac{\omega_d}{2\gamma}$$
* **Nombre:** Factor de calidad $Q$ del oscilador.
* **Situación y Uso:** Parámetro adimensional que mide la eficiencia del oscilador. Cuanto mayor es $Q$, menor es la pérdida relativa de energía por ciclo y más duraderas son las oscilaciones.
* **Variables:**
  * $Q$: Factor de calidad $[\text{adimensional}]$.
  * $|\Delta E|_{	ext{ciclo}}$: Energía disipada en un ciclo $[\text{J}]$.

---

### (19) Ancho de Banda Relativo
* **Fórmula:**
  $$\frac{\Delta \omega}{\omega_0} = \frac{1}{Q}$$
* **Nombre:** Ancho de banda relativo del resueno / Agudeza de resonancia.
* **Situación y Uso:** Relaciona el ancho de la curva de resonancia a media potencia ($\Delta \omega$) con la frecuencia natural. Un alto factor $Q$ implica una curva de respuesta sumamente aguzada o selectiva.
* **Variables:**
  * $\Delta \omega$: Ancho de banda de la respuesta en frecuencia $[\text{rad/s}]$.

---

## 3. Oscilaciones Forzadas y Resonancia

> [!example] **Contexto Físico**
> Un oscilador sujeto a una fuerza externa periódica de impulsión $F(t) = F_0 \cos(\omega_f t)$. El sistema alcanza un régimen permanente oscilando a la frecuencia impulsora $\omega_f$.

### (20) Frecuencia de Resonancia en Amplitud
* **Fórmula:**
  $$\omega_{	ext{res}} = \sqrt{\omega_0^2 - 2\gamma^2}$$
* **Nombre:** Frecuencia angular de resonancia en amplitud.
* **Situación y Uso:** Determina la frecuencia de la fuerza impulsora $\omega_f$ para la cual la amplitud de desplazamiento del oscilador alcanza su valor máximo absoluto.
* **Variables:**
  * $\omega_{	ext{res}}$: Frecuencia de resonancia de amplitud $[\text{rad/s}]$.

---

### (21) Ecuación Diferencial del Oscilador Forzado
* **Fórmula:**
  $$\frac{d^2x}{dt^2} + 2\gamma \frac{dx}{dt} + \omega_0^2 x = F_0 \cos(\omega_f t)$$
* **Nombre:** Ecuación diferencial del oscilador armónico forzado.
* **Situación y Uso:** Modela la dinámica de un oscilador amortiguado accionado por una fuerza externa armónica por unidad de masa ($F_0$).
* **Variables:**
  * $F_0$: Amplitud de la fuerza impulsora por unidad de masa $[\text{N/kg} = 	ext{m/s}^2]$.
  * $\omega_f$: Frecuencia angular de la fuerza impulsora $[\text{rad/s}]$.

---

### (22) Amplitud del Oscilador Forzado en Régimen Permanente
* **Fórmula:**
  $$A = \frac{F_0/m}{\sqrt{(\omega_0^2 - \omega_f^2)^2 + 4\gamma^2 \omega_f^2}}$$
* **Nombre:** Amplitud de oscilación forzada estacionaria.
* **Situación y Uso:** Permite calcular la amplitud constante alcanzada por el sistema en función de la frecuencia impulsora $\omega_f$.
* **Variables:**
  * $A$: Amplitud permanente de oscilación $[\text{m}]$.
  * $F_0/m$: Fuerza impulsora máxima dividida por la masa $[\text{m/s}^2]$.

---

### (23) Desfase entre la Fuerza Impulsora y la Respuesta
* **Fórmula:**
  $$tan\delta = \frac{2\gamma \omega_f}{\omega_0^2 - \omega_f^2}$$
* **Nombre:** Ángulo de desfase $\delta$ en oscilaciones forzadas.
* **Situación y Uso:** Determina cuánto se retrasa la posición del oscilador respecto a la fuerza impulsora externa. En la resonancia ($\omega_f = \omega_0$), $tan\delta \to \infty \implies \delta = \pi/2$.
* **Variables:**
  * $\delta$: Ángulo de desfase $[\text{rad}]$.

---

## 4. Movimiento Ondulatorio y Ondas Mecánicas

> [!abstract] **Contexto Físico**
> Propagación de perturbaciones y energía a través de un medio deformable sin transporte neto de materia.

### (24) Solución General de d'Alembert
* **Fórmula:**
  $$y(x,t) = f(x \mp v t)$$
* **Nombre:** Solución general de la ecuación de onda unidimensional (Solución de d'Alembert).
* **Situación y Uso:** Modela una onda de forma arbitraria $f$ viajando con velocidad constante $v$. El signo ($-$) indica propagación en dirección $+x$ y ($+$) en $-x$.
* **Variables:**
  * $y(x,t)$: Perturbación en la posición $x$ y tiempo $t$.
  * $v$: Velocidad de fase de la onda $[\text{m/s}]$.

---

### (25) Número de Onda Angular
* **Fórmula:**
  $$k = \frac{2\pi}{\lambda}$$
* **Nombre:** Número de onda angular / Constante de propagación espacial.
* **Situación y Uso:** Indica el cambio de fase angular por unidad de distancia recorrida.
* **Variables:**
  * $k$: Número de onda $[\text{rad/m}]$.
  * $\lambda$: Longitud de onda $[\text{m}]$.

---

### (26) Relación Fundamental de Propagación Ondulatoria
* **Fórmula:**
  $$v = \lambda f = \frac{\lambda}{T} = \frac{\omega}{k}$$
* **Nombre:** Velocidad de fase de una onda armónica.
* **Situación y Uso:** Vincula la velocidad de la onda con sus parámetros espaciales ($\lambda, k$) y temporales ($f, T, \omega$).
* **Variables:**
  * $v$: Velocidad de propagación $[\text{m/s}]$.

---

### (27) Ecuación de Onda Armónica Plana
* **Fórmula:**
  $$y(x,t) = y_m \sin(kx - \omega t - \phi)$$
* **Nombre:** Expresión de una onda sinusoidal viajera unidimensional.
* **Situación y Uso:** Describe la perturbación producida por una onda armónica que se desplaza en el sentido positivo del eje $x$.
* **Variables:**
  * $y_m$: Amplitud máxima de la onda $[\text{m}]$.
  * $\phi$: Constante de fase inicial $[\text{rad}]$.

---

### (28) Ecuación Diferencial Clásica de Onda
* **Fórmula:**
$$\frac{\partial^2 y}{\partial t^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial x^2} \quad \left(\text{o } \frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial t^2}\right)$$ 
* **Nombre:** Ecuación diferencial en derivadas parciales de onda unidimensional.
* **Situación y Uso:** Ecuación fundamental que satisface cualquier función de onda no dispersiva que se propaga en un medio homogéneo e isótropo.

---

### (29) Velocidad de Onda Transversal en Cuerda
* **Fórmula:**
  $$v = \sqrt{\frac{T}{\mu}}$$
* **Nombre:** Velocidad de propagación en una cuerda tensa.
* **Situación y Uso:** Calcula la rapidez con la que viajan las ondas mecánicas transversales en una cuerda sometida a una tensión $T$ y con densidad de masa por unidad de longitud $\mu$.
* **Variables:**
  * $T$: Tensión mecánica de la cuerda $[\text{N}]$.
  * $\mu$: Densidad lineal de masa $[\text{kg/m}]$.

---

### (30) Velocidad del Sonido en un Fluido
* **Fórmula:**
  $$v = \sqrt{\frac{B}{ho}}$$
* **Nombre:** Velocidad de ondas longitudinales de presión en un fluido.
* **Situación y Uso:** Expresa la velocidad de propagación del sonido en un medio líquido o gaseoso homogéneo.
* **Variables:**
  * $B$: Módulo de compresibilidad volumétrica (Bulk modulus) $[\text{Pa}]$.
  * $ho$: Densidad volumétrica del fluido $[	ext{kg/m}^3]$.

---

### (31) Velocidad del Sonido en el Aire en función de la Temperatura
* **Fórmula:**
  $$v = 331 \sqrt{1 + \frac{T}{273}}$$
* **Nombre:** Velocidad acústica en aire según la temperatura.
* **Situación y Uso:** Determina la velocidad del sonido en el aire ideal dada la temperatura en grados Celsius $T$.
* **Variables:**
  * $v$: Velocidad del sonido en m/s.
  * $T$: Temperatura ambiental en Celsius $[^\circ\text{C}]$.

---

## 5. Acústica, Intensidad Sonora y Efecto Doppler

> [!tip] **Contexto Físico**
> Estudio de ondas de presión mecánicas auditivas, la energía que transportan por unidad de área y las alteraciones de frecuencia por movimiento relativo de las fuentes.

### (32) Definición General de Intensidad de Onda
* **Fórmula:**
  $$I = \frac{\Delta E}{\Delta t \Delta A} = \frac{P}{\Delta A}$$
* **Nombre:** Intensidad física de una onda.
* **Situación y Uso:** Mide la rapidez con la que se transporta energía por unidad de área normal a la dirección de propagación (potencia $P$ por unidad de superficie).
* **Variables:**
  * $I$: Intensidad $[\text{W/m}^2]$.
  * $P$: Potencia transportada por la onda $[\text{W}]$.
  * $\Delta A$: Área transversal $[\text{m}^2]$.

---

### (33) Intensidad de una Onda Sonora Armónica
* **Fórmula:**
  $$I = \frac{1}{2}
ho v (\omega s_{\text{máx}})^2 =\frac{(\Delta P_{\text{máx}})^2}{2ho v}$$
* **Nombre:** Intensidad sonora en términos de presión y desplazamiento.
* **Situación y Uso:** Evalúa la intensidad de una onda sonora plana a partir de la amplitud de desplazamiento de las moléculas del medio ($s_{\text{máx}}$) o de la variación máxima de presión ($\Delta P_{\text{máx}}$).
* **Variables:**
  * $s_{\text{máx}}$: Amplitud de desplazamiento de partícula $[\text{m}]$.
  * $\Delta P_{\text{máx}}$: Amplitud de la variación de presión $[\text{Pa}]$.

---

### (34) Ley de la Inversa del Cuadrado para Fuentes Puntuales
* **Fórmula:**
  $$I =\frac{P}{4\pi r^2}$$
* **Nombre:** Intensidad de una onda esférica tridimensional.
* **Situación y Uso:** Modela la atenuación de la intensidad sonora producida por una fuente puntual e isótropa de potencia $P$ al alejarse a una distancia $r$.
* **Variables:**
  * $r$: Distancia radial desde la fuente $[\text{m}]$.

---

### (35) Nivel de Intensidad Sonora (Decibelios)
* **Fórmula:**
  $$ \beta = 10 \log\left(\frac{I}{10^{-12}}\right)$$
* **Nombre:** Escala de nivel sonoro en decibelios (dB).
* **Situación y Uso:** Escala logarítmica que cuantifica la sensación auditiva humana respecto al umbral de audición estándar $I_0 = 10^{-12} \text{ W/m}^2$.
* **Variables:**
  * $\beta$: Nivel sonoro en decibelios $[\text{dB}]$.
  * $I$: Intensidad medida $[\text{W/m}^2]$.

---

### (36) Efecto Doppler Acústico
* **Fórmula:**
  $$f' = f \left(\frac{v \pm v_o}{v \mp v_f}\right)$$
* **Nombre:** Ecuación general del Efecto Doppler sonoro.
* **Situación y Uso:** Permite calcular la frecuencia $f'$ percibida por un observador cuando existe movimiento relativo entre la fuente sonora ($v_f$) y el observador ($v_o$) a lo largo de la línea que los une.
* **Regla de signos:** Numerador ($+$ si el observador se acerca, $-$ si se aleja); Denominador ($-$ si la fuente se acerca, $+$ si se aleja).
* **Variables:**
  * $f'$: Frecuencia aparente percibida $[\text{Hz}]$.
  * $f$: Frecuencia propia emitida por la fuente $[\text{Hz}]$.
  * $v$: Velocidad del sonido en el medio $[\text{m/s}]$.
  * $v_o$: Velocidad del observador $[\text{m/s}]$.
  * $v_f$: Velocidad de la fuente $[\text{m/s}]$.

---

## 6. Interferencia, Superposición y Ondas Estacionarias

> [!note] **Contexto Físico**
> Fenómenos derivados del principio de superposición lineal al coincidir dos o más ondas en una misma región del espacio.

### (37) Interferencia de dos Ondas Armónicas Coherentes
* **Fórmula:**
  $$y = 2A \cos\left(\frac{\phi}{2}\right) \sin\left(kx - \omega t + \frac{\phi}{2}\right)$$
* **Nombre:** Onda resultante por interferencia de ondas de igual frecuencia y amplitud con diferencia de fase $\phi$.
* **Situación y Uso:** Describe el perfil de onda resultante de la superposición de dos ondas viajeras idénticas en la misma dirección pero desplazadas en fase una cantidad $\phi$.
* **Variables:**
  * $2A \cos(\phi/2)$: Amplitud de la onda resultante.

---

### (38) Condición de Interferencia Constructiva (Máximos)
* **Fórmula:**
  $$\Delta r = n\lambda \quad (n = 0, 1, 2, \dots)$$
* **Nombre:** Condición de diferencia de camino para interferencia constructiva.
* **Situación y Uso:** Indica las diferencias de distancia $\Delta r$ desde dos fuentes en fase hasta un punto del espacio donde las ondas se refuerzan al máximo.
* **Variables:**
  * $\Delta r$: Diferencia de trayectoria $|r_1 - r_2|$ $[\text{m}]$.
  * $n$: Orden de interferencia (entero positivo).

---

### (39) Condición de Interferencia Destructiva (Mínimos / Nodos)
* **Fórmula:**
  $$\Delta r = \frac{n\lambda}{2} \quad (n = 1, 3, 5, \dots \text{ números impares})$$
* **Nombre:** Condición de diferencia de camino para interferencia destructiva.
* **Situación y Uso:** Muestra la condición espacial en la que dos ondas coherentes en fase se cancelan totalmente debido a una oposición de fase ($\Delta r$ igual a un número impar de medias longitudes de onda).

---

### (40) Ecuación de una Onda Estacionaria
* **Fórmula:**
  $$y = 2A \sin(kx) \cos(\omega t)$$
* **Nombre:** Perfil espacial y temporal de una onda estacionaria.
* **Situación y Uso:** Describe la oscilación fija resultante del choque y superposición de dos ondas idénticas viajando en sentidos opuestos (por ejemplo, ondas confinadas en una cuerda con extremos fijos). No hay transporte neto de energía.
* **Variables:**
  * $2A \sin(kx)$: Amplitud dependiente de la posición.

---

### (41) Posición de los Nodos en Ondas Estacionarias
* **Fórmula:**
  $$x = \frac{n\lambda}{2} \quad (n = 0, 1, 2, \dots)$$
* **Nombre:** Ubicación espacial de nodos de interferencia.
* **Situación y Uso:** Posiciones $x$ a lo largo del medio donde la amplitud de la onda estacionaria es permanentemente igual a cero (puntos en reposo).

---

### (42) Posición de Antinodos (Vientres) en Ondas Estacionarias
* **Fórmula:**
  $$x = \frac{n\lambda}{4} \quad (n = 1, 3, 5, \dots 	ext{ impares})$$
* **Nombre:** Ubicación espacial de antinodos o vientres.
* **Situación y Uso:** Determina los puntos $x$ donde la amplitud de vibración es máxima (igual a $2A$).

---

### (43) Modos Normales de Vibración en Cuerda con Ambos Extremos Fijos
* **Fórmula:**
  $$f_n = \frac{n}{2L}\sqrt{\frac{T}{\mu}} \quad (n = 1, 2, 3, \dots)$$
* **Nombre:** Frecuencias de resonancia / Armónicos en cuerdas fijas.
* **Situación y Uso:** Permite hallar las frecuencias naturales de resonancia de una cuerda de longitud $L$ atada en sus dos extremos ($n=1$ fundamental, $n=2$ segundo armónico, etc.).
* **Variables:**
  * $f_n$: Frecuencia del $n$-ésimo armónico $[\text{Hz}]$.
  * $L$: Longitud de la cuerda $[\text{m}]$.

---

## 7. Ondas Electromagnéticas y Vector de Poynting

> [!abstract] **Contexto Físico**
> Oscilaciones acopladas e interdependientes de campos eléctricos ($\vec{E}$) y magnéticos ($\vec{B}$) que se propagan en el vacío o medos materiales a la velocidad de la luz.

### (44) Campo Eléctrico de una Onda EM Plana
* **Fórmula:**
  $$\vec{E}(x,t) = \hat{j} E_{\text{máx}} \cos(kx \mp \omega t)$$
* **Nombre:** Expresión del campo eléctrico en una onda EM plana monocromática.
* **Situación y Uso:** Describe la oscilación sinusoidal del campo eléctrico orientada según el eje $y$ y propagándose a lo largo del eje $x$.
* **Variables:**
  * $E_{\text{máx}}$: Amplitud del campo eléctrico $[\text{V/m}]$.

---

### (45) Campo Magnético de una Onda EM Plana
* **Fórmula:**
  $$\vec{B}(x,t) = \hat{k} B_{\text{máx}} \cos(kx \mp \omega t)$$
* **Nombre:** Expresión del campo magnético en una onda EM plana.
* **Situación y Uso:** Describe la oscilación del campo de inducción magnética en el eje $z$, perpendicular a $\vec{E}$ y a la dirección de propagación $x$.
* **Variables:**
  * $B_{\text{máx}}$: Amplitud del campo magnético $[\text{T}]$. Nota: $E_{\text{máx}} / B_{\text{máx}} = c$.

---

### (46) Velocidad de Ondas EM en Medios Dieléctricos y Magnéticos
* **Fórmula:**
  $$v = \frac{1}{\sqrt{\epsilon \mu}} = \frac{1}{\sqrt{K K_m}}\frac{1}{\sqrt{\epsilon_0 \mu_0}} = \frac{c}{\sqrt{K K_m}}$$
* **Nombre:** Velocidad de la luz en un medio material.
* **Situación y Uso:** Modela la reducción de la velocidad de las ondas electromagnéticas al atravesar medios no conductores materiales caracterizados por su constante dieléctrica $K$ y permeabilidad $K_m$.
* **Variables:**
  * $c$: Velocidad de la luz en el vacío ($\approx 3 \times 10^8 \text{ m/s}$).
  * $K$: Constante dieléctrica / permitividad relativa.
  * $K_m$: Permeabilidad relativa del medio.

---

### (47) Densidad de Energía Electromagnética Instantánea
* **Fórmula:**
  $$u = \frac{1}{2}\epsilon_0 E^2 + \frac{1}{2\mu_0} B^2 = \epsilon_0 E^2$$
* **Nombre:** Densidad volumétrica de energía en ondas EM.
* **Situación y Uso:** Almacenamiento total de energía por unidad de volumen en los campos eléctrico y magnético de la onda en el vacío. Muestra que la energía se reparte equitativamente entre ambos campos.
* **Variables:**
  * $u$: Densidad de energía $[\text{J/m}^3]$.
  * $\epsilon_0$: Permitividad del vacío ($8.854 \times 10^{-12} \text{ F/m}$).
  * $\mu_0$: Permeabilidad del vacío ($4\pi \times 10^{-7} \text{ H/m}$).

---

### (48) Módulo del Vector de Poynting (Flujo en función de $E$)
* **Fórmula:**
  $$S = \frac{1}{A}\frac{dU}{dt} = \epsilon_0 c E^2 = \frac{\epsilon_0}{\sqrt{\epsilon_0\mu_0}} E^2$$
* **Nombre:** Magnitud instantánea del Vector de Poynting.
* **Situación y Uso:** Representa la tasa instantánea de transferencia de energía electromagnética por unidad de superficie perpendicular a la dirección del flujo.
* **Variables:**
  * $S$: Módulo del vector de Poynting $[\text{W/m}^2]$.

---

### (49) Módulo del Vector de Poynting en función de $E$ y $B$
* **Fórmula:**
  $$S = \sqrt{\frac{\epsilon_0}{\mu_0}} E^2 = \frac{EB}{\mu_0}$$
* **Nombre:** Relación escalar del flujo instantáneo de potencia EM.
* **Situación y Uso:** Expresión equivalente del modulo de Poynting expresada de forma directa mediante las amplitudes instantáneas de los campos $E$ y $B$.

---

### (50) Definición Vectorial del Vector de Poynting
* **Fórmula:**
  $$\vec{S} = \frac{1}{\mu_0} \left(\vec{E} \times \vec{B} \right)$$
* **Nombre:** Vector de Poynting.
* **Situación y Uso:** Vector que especifica la dirección, sentido y densidad de flujo de potencia transportada por los campos electromagnéticos.

---

### (51) Intensidad Promedio de una Onda EM (en función de $E_{\text{máx}}$ y $B_{\text{máx}}$)
* **Fórmula:**
  $$I = S_{\text{prom}} = \frac{E_{\text{máx}} B_{\text{máx}}}{2\mu_0} =\frac{E_{\text{máx}}^2}{2\mu_0 c}$$
* **Nombre:** Intensidad media o irradiancia de una onda EM plana.
* **Situación y Uso:** Evalúa la potencia promedio por unidad de área medida por detectores o superficies expuestas a la radiación continua en el vacío.

---

### (52) Intensidad Promedio EM (con Permitividad del Vacío)
* **Fórmula:**
  $$I = S_{\text{prom}} = \frac{1}{2}\sqrt{\frac{\epsilon_0}{\mu_0}}E_{\text{máx}}^2 = \frac{1}{2}\epsilon_0 c E_{\text{máx}}^2$$
* **Nombre:** Irradiancia en función del campo eléctrico y constantes del vacío.
* **Situación y Uso:** Forma de calcular la intensidad promedio de la luz u onda EM conociendo únicamente la amplitud del campo eléctrico pico $E_{	ext{máx}}$.

---

## 8. Momento, Presión de Radiación e Inercia

> [!important] **Contexto Físico**
> Las ondas electromagnéticas transportan momento lineal ($p$), el cual ejercen como presión o fuerza mecánica al incidir sobre la materia.

### (53) Densidad Volumétrica de Momento Lineal EM
* **Fórmula:**
  $$\frac{dp}{dV} = \frac{EB}{\mu_0 c^2} = \frac{S}{c^2}$$
* **Nombre:** Densidad espacial de momento electromagnético.
* **Situación y Uso:** Representa la cantidad de momento lineal por unidad de volumen almacenada y transportada en los campos EM.
* **Variables:**
  * $\frac{dp}{dV}$: Densidad de momento $[\text{kg}\cdot\text{m}^{-2}\cdot\text{s}^{-1} = \text{N}\cdot\text{s/m}^3]$.

---

### (54) Flujo Temporal de Momento Lineal
* **Fórmula:**
  $$\frac{1}{A} \frac{dp}{dt} = \frac{S}{c} = \frac{EB}{\mu_0 c}$$
* **Nombre:** Flujo de momento por unidad de área (fuerza instantánea específica).
* **Situación y Uso:** Mide la rapidez con la que se transfiere momento a una superficie expuesta a la radiación.

---

### (55) Presión de Radiación sobre Superficie de Absorción Total
* **Fórmula:**
  $$p_{\text{rad}} = \frac{I}{c}$$
* **Nombre:** Presión de radiación para absorción completa (Cuerpo Negro).
* **Situación y Uso:** Calcula la presión mecánica ejercida por la radiación incidente cuando la superficie **absorbe por completo** toda la energía incidente (sin reflexión).
* **Variables:**
  * $p_{\text{rad}}$: Presión de radiación $[\text{Pa} = \text{N/m}^2]$.
  * $I$: Intensidad media de la radiación $[\text{W/m}^2]$.
  * $c$: Velocidad de la luz en el vacío ${[\text{m/s}}]$.

---

### (56) Presión de Radiación sobre Superficie de Reflexión Total
* **Fórmula:**
  $$p_{\text{rad}} = \frac{2I}{c}$$
* **Nombre:** Presión de radiación para reflexión completa (Espejo Perfecto).
* **Situación y Uso:** Mide la presión ejercida cuando la luz es **totalmente reflejada** por un espejo perfecto. Debido al cambio de sentido en el momento de los fotones, la presión ejercida es exactamente el doble que en la absorción total.

---

### (57) Momento de Inercia de una Esfera Sólida Uniforme
* **Fórmula:**
  $$I_{\text{Esfera}} = \frac{2}{5} M R^2$$
* **Nombre:** Momento de inercia de una esfera maciza homogênea.
* **Situación y Uso:** Elemento de mecánica rígida aplicado en oscilaciones rotacionales o péndulos físicos esféricos. Mide la inercia rotacional respecto a un eje que atraviesa su centro geométrico.
* **Variables:**
  * $M$: Masa total de la esfera $[\text{kg}]$.
  * $R$: Radio de la esfera $[\text{m}]$.

---

## 9. Apéndice Matemático

### Desarrollo en Serie del Binomio de Newton
* **Fórmula:**
  $$(1+x)^n = 1 + nx + \frac{n(n-1)}{2!}x^2 + \frac{n(n-1)(n-2)}{3!}x^3 + \dots$$
* **Nombre:** Expansión Binomial de Taylor.
* **Situación y Uso:** Herramienta matemática empleada recurrentemente en física para aproximar expresiones complejas cuando un parámetro es muy pequeño ($|x| \ll 1$). 
* **Ejemplos de aplicación en Física:**
  * Aproximación para pequeñas oscilaciones en péndulos ($\sin\theta \approx \theta$).
  * Correcciones de frecuencia en oscilaciones subamortiguadas ($\omega_d = \omega_0\sqrt{1 - (\gamma/\omega_0)^2} \approx \omega_0 [1 - \frac{1}{2(\gamma/\omega_0)^2}]$).
  * Aproximaciones relativistas para bajas velocidades ($v \ll c$).

---