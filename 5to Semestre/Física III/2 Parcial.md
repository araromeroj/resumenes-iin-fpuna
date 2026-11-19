
# Física III: Movimiento Ondulatorio, Sonido, Armónicos y Ondas Electromagnéticas

> [!ABSTRACT] Resumen del Documento
> Este compendio integra toda la teoría, deducciones, casos particulares y ecuaciones utilizadas en los materiales y presentaciones de clase de Física III (Prof. MSc. Carlos González, FP-UNA). Cubre movimiento ondulatorio en cuerdas, superposición, ondas estacionarias, armónicos en cuerdas y tubos sonoros, acústica, efecto Doppler y ondas electromagnéticas. Cada ecuación incluye el significado estricto de sus símbolos y unidades en el Sistema Internacional (SI).

---

## Unidad 1: Movimiento Ondulatorio y Ondas en una Cuerda

### 1.1 Función de Onda General y Ecuación Diferencial de Onda

Una onda mecánica es una perturbación que se propaga a través de un medio elástico deformable transportando energía y cantidad de movimiento sin transporte neto de materia. Para una onda unidimensional que se propaga a lo largo del eje $x$ con rapidez $v$, la función de onda general es:

$$
\psi(x,t) = f(x \mp vt)
$$

* Signo negativo ($-$): propagación en el sentido positivo del eje $x$ ($+x$).
* Signo positivo ($+$): propagación en el sentido negativo del eje $x$ ($-x$).

Toda función de onda lineal satisface la **ecuación diferencial unidimensional de onda**:

$$
\frac{\partial^2 \psi(x,t)}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 \psi(x,t)}{\partial t^2}
$$

**Significado de los símbolos:**
* $\psi(x,t)$: Magnitud física perturbada en la posición $x$ y tiempo $t$ (desplazamiento, presión, campo eléctrico, etc.).
* $x$: Coordenada espacial de propagación ($\text{m}$).
* $t$: Tiempo ($\text{s}$).
* $v$: Rapidez de propagación de la onda o velocidad de fase ($\text{m/s}$).

---

### 1.2 Función de Onda Armónica (Sinusoidal)

Cuando la fuente oscila con Movimiento Armónico Simple (MAS), se genera una **onda armónica** o periódica. En los apuntes de clase se presenta en dos formas equivalentes:

**Forma general con constantes geométricas:**

$$
\psi(x,t) = A \sin\left[B(x - vt - C)\right]
$$

**Forma estándar en términos de número de onda y frecuencia angular:**

Para propagación hacia $+x$:

$$
y(x,t) = A \sin(kx - \omega t - \phi)
$$

Para propagación hacia $-x$:

$$
y(x,t) = A \sin(kx + \omega t - \phi)
$$

*(Nota: Dependiendo de las condiciones iniciales en $x=0, t=0$, la función también puede expresarse con $\cos(kx \mp \omega t + \phi)$).*

**Significado de los símbolos:**
* $y(x,t)$: Desplazamiento transversal de un elemento del medio respecto al equilibrio ($\text{m}$).
* $A$: Amplitud de la onda; máximo desplazamiento respecto al equilibrio ($\text{m}$).
* $k$: Número de onda angular ($\text{rad/m}$).
* $\omega$: Frecuencia angular ($\text{rad/s}$).
* $\phi$: Constante de fase o ángulo de fase inicial ($\text{rad}$).
* $(kx \mp \omega t - \phi)$: Fase total de la onda ($\text{rad}$).
* $B$: Constante espacial equivalente a $k$ ($\text{rad/m}$).
* $C$: Desplazamiento espacial inicial equivalente a $\phi / k$ ($\text{m}$).

#### Determinación de la Constante de Fase ($\phi$) en Ejercicios de Clase

Para hallar $\phi$ a partir de las condiciones iniciales dadas en el problema, se evalúa la función de onda en $x = 0$ y $t = 0$:

$$
y(0,0) = A \sin(-\phi) = -A \sin(\phi)
$$

Por ejemplo, si en $x=0$ y $t=0$ se cumple $y(0,0) = A$, entonces:

$$
A = -A \sin(\phi) \implies \sin(\phi) = -1 \implies \phi = -\frac{\pi}{2} \text{ rad} \quad \text{o} \quad \phi = \frac{3\pi}{2} \text{ rad}
$$

---

### 1.3 Parámetros Cinemáticos Fundamentales de una Onda

$$
f = \frac{1}{T}
$$

$$
k = \frac{2\pi}{\lambda}
$$

$$
\omega = 2\pi f = \frac{2\pi}{T}
$$

$$
v = \frac{\lambda}{T} = \lambda f = \frac{\omega}{k}
$$

**Significado de los símbolos:**
* $f$: Frecuencia lineal; ciclos por unidad de tiempo ($\text{Hz}$ o $\text{s}^{-1}$).
* $T$: Periodo; tiempo de una oscilación completa ($\text{s}$).
* $\lambda$: Longitud de onda; distancia entre dos crestas o valles consecutivos ($\text{m}$).
* $k$: Número de onda angular ($\text{rad/m}$).
* $\omega$: Frecuencia angular ($\text{rad/s}$).
* $v$: Rapidez de propagación de la onda ($\text{m/s}$).

---

### 1.4 Cinemática Transversal de las Partículas del Medio

Cada elemento $dm$ de la cuerda ejecuta un MAS vertical perpendicular a la propagación de la onda. Su velocidad transversal $u_y$ y aceleración transversal $a_y$ son:

$$
u_y(x,t) = \frac{\partial y(x,t)}{\partial t} = \mp \omega A \cos(kx \mp \omega t - \phi)
$$

$$
u_{y,\text{máx}} = \omega A
$$

$$
a_y(x,t) = \frac{\partial^2 y(x,t)}{\partial t^2} = -\omega^2 A \sin(kx \mp \omega t - \phi) = -\omega^2 y(x,t)
$$

$$
a_{y,\text{máx}} = \omega^2 A
$$

**Significado de los símbolos:**
* $u_y(x,t)$: Velocidad transversal instantánea de una partícula de la cuerda ($\text{m/s}$).
* $u_{y,\text{máx}}$: Rapidez transversal máxima de una partícula ($\text{m/s}$).
* $a_y(x,t)$: Aceleración transversal instantánea de una partícula ($\text{m/s}^2$).
* $a_{y,\text{máx}}$: Aceleración transversal máxima de una partícula ($\text{m/s}^2$).

---

### 1.5 Rapidez de Propagación en una Cuerda Tensa

La rapidez de una onda transversal en un hilo o cuerda estirada depende de la fuerza de tensión $F$ y de la densidad lineal de masa $\mu$:

$$
\mu = \frac{m}{L}
$$

$$
v = \sqrt{\frac{F}{\mu}}
$$

**Significado de los símbolos:**
* $\mu$: Densidad lineal de masa de la cuerda ($\text{kg/m}$).
* $m$: Masa de la cuerda ($\text{kg}$).
* $L$: Longitud de la cuerda ($\text{m}$).
* $F$: Fuerza de tensión en la cuerda ($\text{N}$).
* $v$: Rapidez de la onda transversal ($\text{m/s}$).

> [!TIP] Cuerda Colgante o con Masa Suspendida (Ejercicio Clásico de Examen)
> Si una cuerda pasa por una polea y sostiene un bloque colgante de masa $M_{\text{bloque}}$ en equilibrio, la tensión en la cuerda es igual al peso del bloque:
> $$F = M_{\text{bloque}} \, g$$
> donde $g = 9.8 \text{ m/s}^2$ (o $9.81 \text{ m/s}^2$ según indique el enunciado).

---

### 1.6 Energía y Potencia Transportadas por una Onda en una Cuerda

Para un elemento infinitesimal de masa $dm = \mu \, dx$, su energía cinética infinitesimal es $dK = \frac{1}{2} dm \, u_y^2$. Integrando en una longitud de onda $\lambda$:

$$
K_\lambda = \frac{1}{4} \mu \omega^2 A^2 \lambda
$$

$$
U_\lambda = \frac{1}{4} \mu \omega^2 A^2 \lambda
$$

$$
E_\lambda = K_\lambda + U_\lambda = \frac{1}{2} \mu \omega^2 A^2 \lambda
$$

La potencia media $P$ (rapidez promedio de transferencia de energía en un periodo $T$) es:

$$
P = \frac{E_\lambda}{T} = \frac{1}{2} \mu \omega^2 A^2 v
$$

**Significado de los símbolos:**
* $K_\lambda$: Energía cinética en una longitud de onda ($\text{J}$).
* $U_\lambda$: Energía potencial elástica en una longitud de onda ($\text{J}$).
* $E_\lambda$: Energía mecánica total en una longitud de onda ($\text{J}$).
* $P$: Potencia media transportada por la onda ($\text{W}$).

---

## Unidad 2: Superposición, Ondas Estacionarias y Armónicos

### 2.1 Principio de Superposición e Interferencia

Cuando dos o más ondas viajeras coinciden en la misma región del medio, la función de onda resultante es la suma algebraica de las funciones de onda individuales:

$$
y(x,t) = y_1(x,t) + y_2(x,t)
$$

Si dos ondas sinusoidales de igual amplitud $A$, número de onda $k$ y frecuencia angular $\omega$ viajan en la misma dirección con una diferencia de fase $\phi$:

$$
y_1(x,t) = A \sin(kx - \omega t)
$$

$$
y_2(x,t) = A \sin(kx - \omega t + \phi)
$$

La onda resultante es:

$$
y(x,t) = \left[ 2A \cos\left(\frac{\phi}{2}\right) \right] \sin\left(kx - \omega t + \frac{\phi}{2}\right)
$$

La amplitud resultante $A_{\text{res}}$ es:

$$
A_{\text{res}} = 2A \left|\cos\left(\frac{\phi}{2}\right)\right|
$$

* **Interferencia constructiva máxima:** Ocurre cuando $\phi = 0, 2\pi, 4\pi, \dots = 2m\pi$ ($m = 0, 1, 2, \dots$), o cuando la diferencia de camino $\Delta r = |r_2 - r_1| = m\lambda$. Resulta $A_{\text{res}} = 2A$.
* **Interferencia destructiva total:** Ocurre cuando $\phi = \pi, 3\pi, 5\pi, \dots = (2m + 1)\pi$ ($m = 0, 1, 2, \dots$), o cuando la diferencia de camino $\Delta r = |r_2 - r_1| = \left(m + \frac{1}{2}\right)\lambda$. Resulta $A_{\text{res}} = 0$.

Relación entre diferencia de fase $\Delta \phi$ y diferencia de camino $\Delta r$:

$$
\Delta \phi = \frac{2\pi}{\lambda} \Delta r = k \, \Delta r
$$

**Significado de los símbolos:**
* $A_{\text{res}}$: Amplitud de la onda resultante ($\text{m}$).
* $\phi$ o $\Delta \phi$: Diferencia de fase entre las ondas ($\text{rad}$).
* $\Delta r$: Diferencia de camino recorrido desde las fuentes hasta el punto de observación ($\text{m}$).
* $m$: Orden de interferencia ($0, 1, 2, 3, \dots$).

---

### 2.2 Ondas Estacionarias en una Cuerda

Una **onda estacionaria** se forma por la superposición de dos ondas idénticas (misma amplitud $A$, longitud de onda $\lambda$ y frecuencia $f$) que viajan en sentidos opuestos:

$$
y_1(x,t) = A \sin(kx - \omega t)
$$

$$
y_2(x,t) = A \sin(kx + \omega t)
$$

Aplicando identidades trigonométricas, la función de la onda estacionaria es:

$$
y(x,t) = (2A \sin kx) \cos(\omega t)
$$

*(Nota: Si se utiliza la forma cosenoidal $y_1 = A\cos(kx - \omega t)$ y $y_2 = A\cos(kx + \omega t)$, resulta $y(x,t) = (2A \cos kx)\cos(\omega t)$).*

La amplitud de oscilación en cada posición $x$ es:

$$
A_{\text{est}}(x) = |2A \sin(kx)|
$$

#### Posición de Nodos y Antinodos

* **Nodos (puntos de amplitud nula, $y = 0$ en todo instante):**
  Se producen cuando $\sin(kx) = 0 \implies kx = n\pi$:

$$
x_{\text{nodo}} = n \frac{\lambda}{2} \quad (n = 0, 1, 2, 3, \dots)
$$

* **Antinodos o vientres (puntos de amplitud máxima, $A_{\text{est}} = 2A$):**
  Se producen cuando $|\sin(kx)| = 1 \implies kx = (2n + 1)\frac{\pi}{2}$:

$$
x_{\text{antinodo}} = (2n + 1) \frac{\lambda}{4} \quad (n = 0, 1, 2, 3, \dots)
$$

> [!IMPORTANT] Distancias Características en Ondas Estacionarias
> * Distancia entre dos **nodos consecutivos**: $d_{N-N} = \frac{\lambda}{2}$.
> * Distancia entre dos **antinodos consecutivos**: $d_{A-A} = \frac{\lambda}{2}$.
> * Distancia entre un **nodo y un antinodo adyacente**: $d_{N-A} = \frac{\lambda}{4}$.

---

### 2.3 Modos Normales y Armónicos en una Cuerda Fija en Ambos Extremos

Cuando una cuerda de longitud $L$ está sujeta en ambos extremos ($x=0$ y $x=L$), ambos extremos deben ser **nodos**. Esto impone una cuantización de las longitudes de onda y frecuencias permitidas (modos normales de vibración):

**Longitudes de onda de los modos normales:**

$$
\lambda_n = \frac{2L}{n} \quad (n = 1, 2, 3, \dots)
$$

**Frecuencias naturales o armónicos:**

$$
f_n = \frac{v}{\lambda_n} = n \frac{v}{2L} = \frac{n}{2L} \sqrt{\frac{F}{\mu}} \quad (n = 1, 2, 3, \dots)
$$

**Frecuencia fundamental o primer armónico ($n = 1$):**

$$
f_1 = \frac{v}{2L} = \frac{1}{2L} \sqrt{\frac{F}{\mu}}
$$

**Relación entre el $n$-ésimo armónico y la frecuencia fundamental:**

$$
f_n = n f_1 \quad (n = 1, 2, 3, \dots)
$$

**Significado de los símbolos:**
* $n$: Número de armónico (corresponde también al número de antinodos o husos en la cuerda; $n = 1, 2, 3, \dots$).
* $L$: Longitud de la cuerda vibrante ($\text{m}$).
* $\lambda_n$: Longitud de onda del $n$-ésimo armónico ($\text{m}$).
* $f_n$: Frecuencia del $n$-ésimo armónico ($\text{Hz}$).
* $f_1$: Frecuencia fundamental o primer armónico ($\text{Hz}$).
* $F$: Tensión de la cuerda ($\text{N}$).
* $\mu$: Densidad lineal de masa de la cuerda ($\text{kg/m}$).

> [!NOTE] Nomenclatura de Armónicos y Sobretonos
> * $n = 1$: Primer armónico (Frecuencia fundamental).
> * $n = 2$: Segundo armónico (Primer sobretono).
> * $n = 3$: Tercer armónico (Segundo sobretono).
> * $n$-ésimo armónico: $(n-1)$-ésimo sobretono.
> * En una cuerda fija en ambos extremos, el número de nodos totales (incluyendo los extremos) es $N_{\text{nodos}} = n + 1$, y el número de antinodos es $N_{\text{antinodos}} = n$.

---

### 2.4 Ondas Estacionarias Sonoras y Armónicos en Tubos (Columnas de Aire)

En los tubos sonoros se forman ondas estacionarias longitudinales:
* Un **extremo cerrado** actúa como un **nodo de desplazamiento** (el aire no puede moverse) y un **antinodo de presión**.
* Un **extremo abierto** actúa aproximadamente como un **antinodo de desplazamiento** y un **nodo de presión** (la presión se mantiene igual a la atmosférica, $\Delta P = 0$).

#### Caso A: Tubo Abierto en Ambos Extremos (Todos los armónicos presentes)

Existen antinodos de desplazamiento en ambos extremos ($x=0$ y $x=L$).

**Longitudes de onda permitidas:**

$$
\lambda_n = \frac{2L}{n} \quad (n = 1, 2, 3, \dots)
$$

**Frecuencias de los armónicos:**

$$
f_n = \frac{v}{\lambda_n} = n \frac{v}{2L} = n f_1 \quad (n = 1, 2, 3, \dots)
$$

**Frecuencia fundamental ($n=1$):**

$$
f_1 = \frac{v}{2L}
$$

#### Caso B: Tubo Cerrado en un Extremo y Abierto en el Otro (Solo armónicos impares)

Existe un nodo de desplazamiento en el extremo cerrado ($x=0$) y un antinodo de desplazamiento en el extremo abierto ($x=L$). Solo se excitan los **armónicos impares** ($n = 1, 3, 5, 7, \dots$).

**Longitudes de onda permitidas:**

$$
\lambda_n = \frac{4L}{n} \quad (n = 1, 3, 5, 7, \dots)
$$

**Frecuencias de los armónicos:**

$$
f_n = \frac{v}{\lambda_n} = n \frac{v}{4L} = n f_1 \quad (n = 1, 3, 5, 7, \dots)
$$

**Frecuencia fundamental ($n=1$):**

$$
f_1 = \frac{v}{4L}
$$

*(Nota: En un tubo cerrado en un extremo, el primer sobretono corresponde a $n=3$, es decir, $f_3 = 3f_1$; el segundo sobretono corresponde a $n=5$, es decir, $f_5 = 5f_1$).*

**Significado de los símbolos:**
* $L$: Longitud de la columna de aire o del tubo ($\text{m}$).
* $v$: Rapidez del sonido en el gas dentro del tubo ($\text{m/s}$).
* $\lambda_n$: Longitud de onda del modo normal $n$ ($\text{m}$).
* $f_n$: Frecuencia del $n$-ésimo armónico ($\text{Hz}$).
* $f_1$: Frecuencia fundamental ($\text{Hz}$).
* $n$: Índice del armónico ($1, 2, 3, \dots$ para tubo abierto-abierto; $1, 3, 5, \dots$ para tubo cerrado-abierto).

---

### 2.5 Pulsaciones o Batidos (Interferencia Temporal)

Cuando dos ondas sonoras de igual amplitud $A$ pero frecuencias ligeramente diferentes $f_1$ y $f_2$ se superponen en un mismo punto, se produce una variación periódica de la amplitud llamada **pulsación** o **batido**:

$$
y(t) = \left[ 2A \cos\left(2\pi \frac{f_1 - f_2}{2} t\right) \right] \cos\left(2\pi \frac{f_1 + f_2}{2} t\right)
$$

**Frecuencia de pulsación o frecuencia de batido ($f_{\text{batido}}$):**

$$
f_{\text{batido}} = |f_1 - f_2|
$$

**Frecuencia percibida (tono promedio):**

$$
f_{\text{prom}} = \frac{f_1 + f_2}{2}
$$

**Significado de los símbolos:**
* $f_{\text{batido}}$: Número de máximos de intensidad sonora escuchados por segundo ($\text{Hz}$).
* $f_1, f_2$: Frecuencias individuales de las dos fuentes sonoras ($\text{Hz}$).
* $f_{\text{prom}}$: Frecuencia del tono resultante percibido ($\text{Hz}$).

---

## Unidad 3: Ondas Sonoras (Acústica y Efecto Doppler)

### 3.1 Ecuaciones de Desplazamiento y de Presión Sonora

En las presentaciones de clase del Prof. Carlos González, la onda sonora longitudinal se expresa mediante el desplazamiento $s(x,t)$ y la fluctuación de presión $\Delta P(x,t)$:

$$
s(x,t) = s_{\text{máx}} \sin(kx - \omega t - \phi)
$$

$$
\Delta P(x,t) = \Delta P_{\text{máx}} \cos(kx - \omega t - \phi)
$$

*(Nota: Si el desplazamiento se define como $s(x,t) = s_{\text{máx}} \cos(kx - \omega t)$, entonces $\Delta P(x,t) = \Delta P_{\text{máx}} \sin(kx - \omega t)$. En ambos casos existe un desfase de $\frac{\pi}{2}\text{ rad}$ entre presión y desplazamiento).*

**Amplitud de presión máxima ($\Delta P_{\text{máx}}$):**

$$
\Delta P_{\text{máx}} = \rho v \omega s_{\text{máx}} = B k s_{\text{máx}} = K k s_{\text{máx}}
$$

**Significado de los símbolos:**
* $s(x,t)$: Desplazamiento longitudinal instantáneo de los elementos del medio ($\text{m}$).
* $s_{\text{máx}}$: Amplitud de desplazamiento ($\text{m}$).
* $\Delta P(x,t)$: Variación instantánea de presión respecto a la presión de equilibrio ($\text{Pa}$).
* $\Delta P_{\text{máx}}$: Amplitud de presión ($\text{Pa}$).
* $\rho$: Densidad volumétrica del medio ($\text{kg/m}^3$).
* $v$: Rapidez del sonido en el medio ($\text{m/s}$).
* $\omega$: Frecuencia angular ($\text{rad/s}$).
* $K$ o $B$: Módulo de compresibilidad volumétrica del fluido ($\text{Pa}$).

---

### 3.2 Rapidez del Sonido en Sólidos, Líquidos y Gases

**1. En barras o varillas sólidas delgadas:**

$$
v = \sqrt{\frac{Y}{\rho}}
$$

**2. En líquidos o fluidos:**

$$
v = \sqrt{\frac{K}{\rho}} = \sqrt{\frac{B}{\rho}}
$$

**3. En gases ideales:**

$$
v = \sqrt{\frac{\gamma R T}{M}} = \sqrt{\frac{\gamma P_0}{\rho}}
$$

**4. En el aire en función de la temperatura Celsius ($T_C$):**

$$
v = (331 \text{ m/s}) \sqrt{1 + \frac{T_C}{273^\circ\text{C}}}
$$

**Significado de los símbolos:**
* $Y$: Módulo de Young del material sólido ($\text{Pa}$).
* $K$ o $B$: Módulo de compresibilidad del fluido ($\text{Pa}$).
* $\rho$: Densidad del medio ($\text{kg/m}^3$).
* $\gamma$: Coeficiente adiabático del gas ($\gamma = 1.40$ para el aire y gases diatómicos; $\gamma = 1.67$ para gases monoatómicos).
* $R$: Constante universal de los gases ideales ($8.314 \text{ J/mol}\cdot\text{K}$).
* $T$: Temperatura absoluta en Kelvin ($T = T_C + 273.15$, en $\text{K}$).
* $M$: Masa molar del gas ($\text{kg/mol}$).
* $P_0$: Presión de equilibrio del gas ($\text{Pa}$).
* $T_C$: Temperatura en grados Celsius ($^\circ\text{C}$).

---

### 3.3 Intensidad de Ondas Sonoras y Ondas Esféricas

**Definición general de intensidad sonora:**

$$
I \equiv \frac{\Delta E}{\Delta t \, \Delta A} = \frac{P}{\Delta A}
$$

**Intensidad en función de las amplitudes de desplazamiento y presión:**

$$
I = \frac{1}{2} \rho v (\omega s_{\text{máx}})^2 = \frac{(\Delta P_{\text{máx}})^2}{2 \rho v}
$$

**Intensidad de ondas sonoras esféricas (fuente puntual isotrópica):**

$$
I = \frac{P_{\text{prom}}}{A} = \frac{P_{\text{prom}}}{4\pi r^2}
$$

$$
I \propto \frac{1}{r^2} \implies \frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}
$$

**Significado de los símbolos:**
* $I$: Intensidad sonora ($\text{W/m}^2$).
* $P$ o $P_{\text{prom}}$: Potencia acústica promedio ($\text{W}$).
* $\Delta A$ o $A$: Área perpendicular a la dirección de propagación ($\text{m}^2$).
* $r$: Distancia radial desde la fuente puntual hasta el punto de recepción ($\text{m}$).

---

### 3.4 Nivel de Intensidad Sonora (Decibeles)

$$
\beta = 10 \log_{10} \left( \frac{I}{I_0} \right)
$$

Despeje para hallar la intensidad $I$ a partir del nivel sonoro $\beta$:

$$
I = I_0 \cdot 10^{\beta / 10}
$$

Diferencia de niveles sonoros entre dos intensidades $I_1$ e $I_2$:

$$
\Delta \beta = \beta_2 - \beta_1 = 10 \log_{10} \left( \frac{I_2}{I_1} \right)
$$

**Significado de los símbolos:**
* $\beta$: Nivel de intensidad sonora en decibeles ($\text{dB}$).
* $I$: Intensidad sonora ($\text{W/m}^2$).
* $I_0$: Intensidad de referencia del umbral de audición ($I_0 = 1.0 \times 10^{-12} \text{ W/m}^2$).

---

### 3.5 Efecto Doppler (Todos los Casos de las Presentaciones de Clase)

En los apuntes de clase se presentan los casos individuales y la ecuación unificada:

**Caso 1: Fuente en reposo ($v_F = 0$) y observador en movimiento ($v_O$):**
* Observador acercándose a la fuente:
  $$f' = f \left( \frac{v + v_O}{v} \right)$$
* Observador alejándose de la fuente:
  $$f' = f \left( \frac{v - v_O}{v} \right)$$

**Caso 2: Observador en reposo ($v_O = 0$) y fuente en movimiento ($v_F$):**
* Fuente acercándose al observador:
  $$f' = f \left( \frac{v}{v - v_F} \right)$$
* Fuente alejándose del observador:
  $$f' = f \left( \frac{v}{v + v_F} \right)$$

**Caso 3: Ecuación General (Fuente y observador en movimiento simultáneo):**

$$
f' = f \left( \frac{v \pm v_O}{v \mp v_F} \right)
$$

**Longitud de onda aparente delante y detrás de una fuente en movimiento:**
* Delante de la fuente (acercándose al observador):
  $$\lambda' = \lambda - \frac{v_F}{f} = \frac{v - v_F}{f}$$
* Detrás de la fuente (alejándose del observador):
  $$\lambda' = \lambda + \frac{v_F}{f} = \frac{v + v_F}{f}$$

**Ondas de Choque y Número de Mach (cuando $v_F > v$):**

$$
\sin \theta = \frac{v}{v_F} = \frac{1}{M_{\text{Mach}}}
$$

**Significado de los símbolos:**
* $f'$: Frecuencia aparente percibida por el observador ($\text{Hz}$).
* $f$: Frecuencia real emitida por la fuente ($\text{Hz}$).
* $v$: Rapidez del sonido en el medio ($\text{m/s}$).
* $v_O$: Rapidez del observador respecto al aire ($\text{m/s}$).
* $v_F$: Rapidez de la fuente respecto al aire ($\text{m/s}$).
* $\lambda'$: Longitud de onda aparente ($\text{m}$).
* $\theta$: Semiángulo del cono de Mach ($\text{rad}$ o grados).
* $M_{\text{Mach}} = v_F / v$: Número de Mach (adimensional).

---

## Unidad 4: Ondas Electromagnéticas

### 4.1 Las Ecuaciones de Maxwell en el Vacío

**1. Ley de Gauss para el campo eléctrico:**

$$
\oint \vec{E} \cdot d\vec{A} = \frac{q_{\text{enc}}}{\epsilon_0}
$$

**2. Ley de Gauss para el magnetismo:**

$$
\oint \vec{B} \cdot d\vec{A} = 0
$$

**3. Ley de inducción de Faraday:**

$$
\oint \vec{E} \cdot d\vec{\ell} = -\frac{d\Phi_B}{dt}
$$

**4. Ley de Ampère-Maxwell:**

$$
\oint \vec{B} \cdot d\vec{\ell} = \mu_0 \left( i_C + \epsilon_0 \frac{d\Phi_E}{dt} \right)
$$

**Corriente de desplazamiento de Maxwell:**

$$
i_D = \epsilon_0 \frac{d\Phi_E}{dt}
$$

**Significado de los símbolos:**
* $\vec{E}$: Vector de campo eléctrico ($\text{N/C}$ o $\text{V/m}$).
* $\vec{B}$: Vector de campo magnético ($\text{T}$).
* $d\vec{A}$: Vector diferencial de área ($\text{m}^2$).
* $d\vec{\ell}$: Vector diferencial de longitud ($\text{m}$).
* $q_{\text{enc}}$: Carga eléctrica encerrada ($\text{C}$).
* $\epsilon_0$: Permitividad eléctrica del vacío ($8.854 \times 10^{-12} \text{ C}^2/\text{N}\cdot\text{m}^2$).
* $\mu_0$: Permeabilidad magnética del vacío ($4\pi \times 10^{-7} \text{ T}\cdot\text{m/A}$).
* $\Phi_B = \int \vec{B} \cdot d\vec{A}$: Flujo magnético ($\text{Wb}$).
* $\Phi_E = \int \vec{E} \cdot d\vec{A}$: Flujo eléctrico ($\text{N}\cdot\text{m}^2/\text{C}$).
* $i_C$: Corriente de conducción ($\text{A}$).
* $i_D$: Corriente de desplazamiento ($\text{A}$).

---

### 4.2 Ondas Electromagnéticas Planas y Rapidez de la Luz

**Ecuaciones diferenciales de onda electromagnética en el vacío:**

$$
\frac{\partial^2 E}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 E}{\partial t^2} \quad ; \quad \frac{\partial^2 B}{\partial x^2} = \mu_0 \epsilon_0 \frac{\partial^2 B}{\partial t^2}
$$

**Rapidez de la luz en el vacío ($c$):**

$$
c = \frac{1}{\sqrt{\mu_0 \epsilon_0}} \approx 3.00 \times 10^8 \text{ m/s}
$$

**Funciones de onda para una onda electromagnética plana sinusoidal:**

$$
E(x,t) = E_{\text{máx}} \cos(kx - \omega t) \quad \text{o} \quad E(x,t) = E_{\text{máx}} \sin(kx - \omega t)
$$

$$
B(x,t) = B_{\text{máx}} \cos(kx - \omega t) \quad \text{o} \quad B(x,t) = B_{\text{máx}} \sin(kx - \omega t)
$$

**Relación entre las magnitudes de $\vec{E}$ y $\vec{B}$ en el vacío:**

$$
B = \frac{E}{c} = \sqrt{\epsilon_0 \mu_0} \, E \implies \frac{E}{B} = \frac{E_{\text{máx}}}{B_{\text{máx}}} = c
$$

$$
c = \lambda f = \frac{\omega}{k}
$$

**Significado de los símbolos:**
* $E(x,t)$, $B(x,t)$: Magnitudes instantáneas de los campos eléctrico ($\text{V/m}$) y magnético ($\text{T}$).
* $E_{\text{máx}}$, $B_{\text{máx}}$: Amplitudes de los campos eléctrico ($\text{V/m}$) y magnético ($\text{T}$).
* $c$: Rapidez de la luz en el vacío ($2.9979 \times 10^8 \text{ m/s}$).

---

### 4.3 Índice de Refracción y Propagación en Medios Materiales

**Rapidez de la onda electromagnética en un medio material:**

$$
v = \frac{1}{\sqrt{\mu \epsilon}} = \frac{c}{n}
$$

**Índice de refracción absoluto ($n$):**

$$
n = \frac{c}{v} = \sqrt{\frac{\mu \epsilon}{\mu_0 \epsilon_0}} = \sqrt{\kappa_m \kappa_e} \approx \sqrt{\kappa_e}
$$

**Relación entre campos $E$ y $B$ dentro de un medio material:**

$$
\frac{E}{B} = v = \frac{c}{n}
$$

**Longitud de onda en un medio de índice de refracción $n$ (la frecuencia $f$ no cambia):**

$$
\lambda_n = \frac{\lambda_0}{n}
$$

**Significado de los símbolos:**
* $v$: Rapidez de la onda electromagnética en el medio ($\text{m/s}$).
* $n$: Índice de refracción del medio (adimensional).
* $\epsilon$: Permitividad eléctrica del medio ($\text{C}^2/\text{N}\cdot\text{m}^2$).
* $\mu$: Permeabilidad magnética del medio ($\text{T}\cdot\text{m/A}$).
* $\kappa_e$: Constante dieléctrica del medio (adimensional).
* $\kappa_m$: Permeabilidad relativa del medio ($\kappa_m \approx 1$ en dieléctricos no magnéticos).
* $\lambda_0$: Longitud de onda en el vacío ($\text{m}$).
* $\lambda_n$: Longitud de onda en el medio ($\text{m}$).

---

### 4.4 Densidad de Energía, Vector de Poynting, Intensidad y Presión de Radiación

**Densidad de energía eléctrica ($u_E$) y magnética ($u_B$):**

$$
u_E = \frac{1}{2} \epsilon_0 E^2 \quad ; \quad u_B = \frac{B^2}{2\mu_0} \quad ; \quad u_E = u_B
$$

**Densidad de energía electromagnética total instantánea ($u$) y promedio ($u_{\text{prom}}$):**

$$
u = u_E + u_B = \epsilon_0 E^2 = \frac{B^2}{\mu_0}
$$

$$
u_{\text{prom}} = \frac{1}{2} \epsilon_0 E_{\text{máx}}^2 = \frac{B_{\text{máx}}^2}{2\mu_0} = \epsilon_0 E_{\text{rms}}^2 = \frac{B_{\text{rms}}^2}{\mu_0}
$$

**Valores eficaces (RMS) de los campos:**

$$
E_{\text{rms}} = \frac{E_{\text{máx}}}{\sqrt{2}} \quad ; \quad B_{\text{rms}} = \frac{B_{\text{máx}}}{\sqrt{2}}
$$

**Vector de Poynting ($\vec{S}$):**

$$
\vec{S} = \frac{1}{\mu_0} (\vec{E} \times \vec{B})
$$

**Magnitud instantánea del vector de Poynting:**

$$
S = \frac{E B}{\mu_0} = \frac{E^2}{\mu_0 c} = \frac{c B^2}{\mu_0} = c u
$$

**Intensidad de la onda electromagnética ($I = \bar{S} = S_{\text{prom}}$):**

$$
I = \bar{S} = \frac{E_{\text{máx}} B_{\text{máx}}}{2\mu_0} = \frac{E_{\text{máx}}^2}{2\mu_0 c} = \frac{c B_{\text{máx}}^2}{2\mu_0} = \frac{E_{\text{rms}} B_{\text{rms}}}{\mu_0} = c u_{\text{prom}}
$$

**Intensidad de una fuente puntual isotrópica de potencia media $P_{\text{prom}}$:**

$$
I = \frac{P_{\text{prom}}}{4\pi r^2}
$$

**Cantidad de movimiento lineal ($p$) y Fuerza de radiación ($F_{\text{rad}}$):**
* **Absorción total:**
  $$p = \frac{U}{c} \quad ; \quad F_{\text{rad}} = \frac{I A}{c} = \frac{P_{\text{abs}}}{c}$$
* **Reflexión total (incidencia normal):**
  $$p = \frac{2U}{c} \quad ; \quad F_{\text{rad}} = \frac{2 I A}{c} = \frac{2 P_{\text{refl}}}{c}$$

**Presión de radiación ($p_{\text{rad}}$ o $P_{\text{rad}}$) (Ecuación 20 de la presentación):**
* **Absorción total:**
  $$p_{\text{rad}} = \frac{\bar{S}}{c} = \frac{I}{c}$$
* **Reflexión total:**
  $$p_{\text{rad}} = \frac{2\bar{S}}{c} = \frac{2I}{c}$$

**Significado de los símbolos:**
* $u_E, u_B, u$: Densidades de energía eléctrica, magnética y total instantánea ($\text{J/m}^3$).
* $u_{\text{prom}}$: Densidad de energía promedio ($\text{J/m}^3$).
* $E_{\text{rms}}, B_{\text{rms}}$: Valores cuadráticos medios (eficaces) de los campos ($\text{V/m}$ y $\text{T}$).
* $\vec{S}$: Vector de Poynting; densidad de flujo de potencia instantánea ($\text{W/m}^2$).
* $I$ o $\bar{S}$: Intensidad de la onda electromagnética ($\text{W/m}^2$).
* $P_{\text{prom}}$: Potencia promedio emitida por la fuente ($\text{W}$).
* $r$: Distancia radial desde la fuente ($\text{m}$).
* $p$: Cantidad de movimiento transferida ($\text{kg}\cdot\text{m/s}$).
* $U$: Energía electromagnética transferida ($\text{J}$).
* $F_{\text{rad}}$: Fuerza ejercida por la radiación sobre un área $A$ ($\text{N}$).
* $p_{\text{rad}}$: Presión de radiación ($\text{Pa}$ o $\text{N/m}^2$).

---

## Tabla Resumen Completa de Fórmulas de Clase

| Nombre de la Fórmula | Fórmula Matemática | Descripción Física |
| :--- | :--- | :--- |
| **Función de onda general** | $\psi(x,t) = f(x \mp vt)$ | Perturbación que viaja hacia $+x$ ($-$) o $-x$ ($+$) con rapidez $v$. |
| **Ecuación diferencial de onda** | $\frac{\partial^2 \psi}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 \psi}{\partial t^2}$ | Ecuación diferencial lineal que gobierna toda onda mecánica o electromagnética. |
| **Onda armónica (forma general)** | $\psi(x,t) = A \sin\left[B(x - vt - C)\right]$ | Expresión sinusoidal en función de las constantes espaciales $B=k$ y $C=\phi/k$. |
| **Onda armónica (estándar)** | $y(x,t) = A \sin(kx \mp \omega t - \phi)$ | Desplazamiento transversal de una onda sinusoidal hacia $+x$ ($-$) o $-x$ ($+$). |
| **Periodo y frecuencia** | $f = \frac{1}{T}$ | Relación inversa entre el número de ciclos por segundo y el tiempo de un ciclo. |
| **Número de onda angular** | $k = \frac{2\pi}{\lambda}$ | Radianes de fase por unidad de distancia. |
| **Frecuencia angular** | $\omega = 2\pi f = \frac{2\pi}{T}$ | Radianes de fase por unidad de tiempo. |
| **Rapidez de propagación** | $v = \lambda f = \frac{\lambda}{T} = \frac{\omega}{k}$ | Relación cinemática fundamental invariante para cualquier onda periódica. |
| **Velocidad transversal de partícula** | $u_y(x,t) = \frac{\partial y}{\partial t} = \mp \omega A \cos(kx \mp \omega t - \phi)$ | Velocidad vertical instantánea de un elemento de la cuerda en MAS ($u_{y,\text{máx}} = \omega A$). |
| **Aceleración transversal de partícula** | $a_y(x,t) = \frac{\partial^2 y}{\partial t^2} = -\omega^2 y(x,t)$ | Aceleración vertical instantánea de un elemento de la cuerda ($a_{y,\text{máx}} = \omega^2 A$). |
| **Densidad lineal de masa** | $\mu = \frac{m}{L}$ | Masa por unidad de longitud de una cuerda o alambre uniforme. |
| **Rapidez de onda en cuerda** | $v = \sqrt{\frac{F}{\mu}}$ | Velocidad de propagación transversal determinada por la tensión $F$ y la inercia $\mu$. |
| **Energía en una longitud de onda** | $E_\lambda = \frac{1}{2} \mu \omega^2 A^2 \lambda$ | Energía mecánica total ($K_\lambda + U_\lambda$) contenida en una longitud de onda $\lambda$. |
| **Potencia media en cuerda** | $P = \frac{1}{2} \mu \omega^2 A^2 v$ | Rapidez promedio de transferencia de energía a lo largo de la cuerda. |
| **Amplitud por interferencia** | $A_{\text{res}} = 2A \left|\cos\left(\frac{\phi}{2}\right)\right|$ | Amplitud resultante de dos ondas idénticas con diferencia de fase $\phi = \frac{2\pi}{\lambda}\Delta r$. |
| **Onda estacionaria en cuerda** | $y(x,t) = (2A \sin kx)\cos(\omega t)$ | Superposición de dos ondas idénticas que viajan en sentidos opuestos. |
| **Posición de nodos** | $x_{\text{nodo}} = n \frac{\lambda}{2} \quad (n = 0,1,2,\dots)$ | Puntos de una onda estacionaria donde la amplitud es siempre cero. |
| **Posición de antinodos** | $x_{\text{antinodo}} = (2n + 1) \frac{\lambda}{4} \quad (n = 0,1,2,\dots)$ | Puntos de una onda estacionaria donde la amplitud es máxima ($2A$). |
| **Armónicos en cuerda fija** | $\lambda_n = \frac{2L}{n} \quad ; \quad f_n = \frac{n}{2L}\sqrt{\frac{F}{\mu}} = n f_1$ | Modos normales de vibración ($n = 1, 2, 3, \dots$) para una cuerda fija en ambos extremos. |
| **Armónicos en tubo abierto-abierto** | $\lambda_n = \frac{2L}{n} \quad ; \quad f_n = n \frac{v}{2L} = n f_1$ | Todos los armónicos ($n = 1, 2, 3, \dots$) en un tubo abierto en ambos extremos. |
| **Armónicos en tubo cerrado-abierto** | $\lambda_n = \frac{4L}{n} \quad ; \quad f_n = n \frac{v}{4L} = n f_1$ | Solo armónicos impares ($n = 1, 3, 5, \dots$) en un tubo cerrado en un extremo. |
| **Frecuencia de pulsación (batidos)** | $f_{\text{batido}} = |f_1 - f_2|$ | Frecuencia de modulación de amplitud al superponer dos sonidos de frecuencias cercanas. |
| **Onda sonora de desplazamiento** | $s(x,t) = s_{\text{máx}} \sin(kx - \omega t - \phi)$ | Oscilación longitudinal de las partículas del medio en una onda acústica. |
| **Onda sonora de presión** | $\Delta P(x,t) = \Delta P_{\text{máx}} \cos(kx - \omega t - \phi)$ | Fluctuación de presión desfasada $\pi/2$ respecto al desplazamiento $s(x,t)$. |
| **Amplitud de presión sonora** | $\Delta P_{\text{máx}} = \rho v \omega s_{\text{máx}} = K k s_{\text{máx}}$ | Máxima variación de presión respecto a la presión atmosférica o de equilibrio. |
| **Rapidez del sonido en sólidos** | $v = \sqrt{\frac{Y}{\rho}}$ | Velocidad de propagación longitudinal en una barra sólida (módulo de Young $Y$). |
| **Rapidez del sonido en líquidos** | $v = \sqrt{\frac{K}{\rho}} = \sqrt{\frac{B}{\rho}}$ | Velocidad del sonido en fluidos (módulo de compresibilidad $K$ o $B$). |
| **Rapidez del sonido en gases ideales** | $v = \sqrt{\frac{\gamma R T}{M}} = \sqrt{\frac{\gamma P_0}{\rho}}$ | Velocidad acústica en un gas ideal en función de su temperatura absoluta $T$. |
| **Rapidez del sonido en aire ($T_C$)** | $v = 331 \sqrt{1 + \frac{T_C}{273}}$ | Rapidez del sonido en el aire en función de la temperatura en grados Celsius. |
| **Intensidad sonora (onda plana)** | $I = \frac{P}{\Delta A} = \frac{1}{2}\rho v (\omega s_{\text{máx}})^2 = \frac{(\Delta P_{\text{máx}})^2}{2\rho v}$ | Potencia acústica promedio transportada por unidad de área perpendicular. |
| **Intensidad sonora esférica** | $I = \frac{P_{\text{prom}}}{4\pi r^2} \implies \frac{I_1}{I_2} = \frac{r_2^2}{r_1^2}$ | Ley del inverso del cuadrado para ondas esféricas emitidas isotrópicamente. |
| **Nivel de intensidad sonora** | $\beta = 10 \log_{10} \left( \frac{I}{I_0} \right)$ | Nivel sonoro en decibeles ($\text{dB}$) respecto al umbral $I_0 = 10^{-12} \text{ W/m}^2$. |
| **Efecto Doppler (general)** | $f' = f \left( \frac{v \pm v_O}{v \mp v_F} \right)$ | Frecuencia aparente $f'$ ($+$ acercamiento, $-$ alejamiento para $v_O$; signos opuestos para $v_F$). |
| **Cono de Mach (ondas de choque)** | $\sin \theta = \frac{v}{v_F} = \frac{1}{M_{\text{Mach}}}$ | Ángulo del frente de onda supersónico cuando la fuente supera la rapidez del sonido ($v_F > v$). |
| **Ecuaciones de Maxwell (vacío)** | $\oint \vec{E}\cdot d\vec{A} = \frac{q_{\text{enc}}}{\epsilon_0}$ ; $\oint \vec{B}\cdot d\vec{A} = 0$<br>$\oint \vec{E}\cdot d\vec{\ell} = -\frac{d\Phi_B}{dt}$ ; $\oint \vec{B}\cdot d\vec{\ell} = \mu_0(i_C + \epsilon_0\frac{d\Phi_E}{dt})$ | Las cuatro leyes fundamentales que unifican el electromagnetismo y predicen las ondas EM. |
| **Rapidez de la luz en el vacío** | $c = \frac{1}{\sqrt{\mu_0 \epsilon_0}} \approx 3.00 \times 10^8 \text{ m/s}$ | Rapidez universal de propagación de toda onda electromagnética en el espacio libre. |
| **Relación entre campos $E$ y $B$** | $B = \frac{E}{c} = \sqrt{\epsilon_0 \mu_0} \, E \implies \frac{E_{\text{máx}}}{B_{\text{máx}}} = c$ | Proporción constante entre los campos eléctrico y magnético oscilantes en fase. |
| **Índice de refracción** | $n = \frac{c}{v} = \sqrt{\frac{\mu \epsilon}{\mu_0 \epsilon_0}} = \frac{\lambda_0}{\lambda_n}$ | Factor de disminución de la rapidez y longitud de onda dentro de un medio material. |
| **Densidad de energía EM** | $u = \epsilon_0 E^2 = \frac{B^2}{\mu_0}$ ; $u_{\text{prom}} = \frac{1}{2}\epsilon_0 E_{\text{máx}}^2$ | Energía electromagnética almacenada por unidad de volumen en los campos $\vec{E}$ y $\vec{B}$. |
| **Vector de Poynting** | $\vec{S} = \frac{1}{\mu_0} (\vec{E} \times \vec{B})$ | Vector que indica la dirección de propagación y el flujo de potencia instantánea ($\text{W/m}^2$). |
| **Intensidad de onda EM** | $I = \bar{S} = \frac{E_{\text{máx}} B_{\text{máx}}}{2\mu_0} = \frac{E_{\text{máx}}^2}{2\mu_0 c} = \frac{c B_{\text{máx}}^2}{2\mu_0}$ | Promedio temporal del vector de Poynting; potencia media por unidad de área. |
| **Cantidad de movimiento EM** | $p = \frac{U}{c}$ (abs.) ; $p = \frac{2U}{c}$ (refl.) | Momento lineal transferido por una onda electromagnética al incidir sobre una superficie. |
| **Presión de radiación** | $p_{\text{rad}} = \frac{\bar{S}}{c} = \frac{I}{c}$ (abs.) ; $p_{\text{rad}} = \frac{2\bar{S}}{c} = \frac{2I}{c}$ (refl.) | Presión mecánica ejercida por la radiación electromagnética sobre una superficie. |