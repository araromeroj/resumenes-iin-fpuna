# Unidad II: Ecuación de Estado y Teoría Cinético-Molecular

## 1. Conceptos Fundamentales de Sistemas Termodinámicos

* **Sistema:** Porción del espacio delimitada (por fronteras reales o imaginarias) que se aísla para su estudio.
* **Entorno:** Cualquier región exterior al sistema que puede interactuar e intercambiar energía o materia con él.
* **Clasificación de Sistemas:**
  * **Cerrado:** Intercambia energía pero no masa con el entorno.
  * **Abierto:** Intercambia energía y masa con el entorno.
  * **Aislado:** No intercambia ni energía ni masa con el entorno.
* **Estado de un Sistema:** Condición definida cuantitativamente por los valores de sus variables macroscópicas (presión $p$, temperatura $T$, volumen $V$, masa $m$ o moles $n$).
* **Tipos de Procesos Termodinámicos:**
  * **Cuasiestático:** El cambio ocurre tan lentamente que el sistema pasa por una sucesión de estados de equilibrio.
  * **No cuasiestático:** Ocurre de forma rápida mediante variaciones finitas no equilibradas.
  * **Reversible:** Proceso cuyo sentido puede invertirse mediante un cambio infinitesimal en las propiedades del sistema (todo proceso reversible es cuasiestático).
  * **Irreversible:** Ocurre con diferencias finitas de propiedades y genera entropía.
  * **Isotérmico:** Se realiza a temperatura constante ($T = \text{constante}$).
  * **Isobárico:** Se realiza a presión constante ($p = \text{constante}$).
  * **Isocórico (o Isométrico):** Se realiza a volumen constante ($V = \text{constante}$).
  * **Adiabático:** Ocurre sin intercambio de calor entre el sistema y el entorno ($Q = 0$).

---

## 2. Ecuación de Estado del Gas Ideal

La ecuación de estado relaciona las variables macroscópicas que describen el estado termodinámico de una sustancia.

### 2.1 Ecuación en Función de Moles y Masa
Para un gas ideal a baja presión y alta temperatura:

$$
p V = n R T
$$

Donde:
* $p$: Presión absoluta ($\text{Pa}$ o $\text{N/m}^2$).
* $V$: Volumen ($\text{m}^3$).
* $n$: Cantidad de sustancia ($\text{moles}$).
* $T$: Temperatura absoluta ($\text{K}$).
* $R$: Constante universal de los gases ideales.
  * $R = 8,3145 \, \frac{\text{J}}{\text{mol} \cdot \text{K}}$
  * $R = 0,08206 \, \frac{\text{L} \cdot \text{atm}}{\text{mol} \cdot \text{K}}$

Sabiendo que el número de moles es $n = \frac{m_{\text{total}}}{M}$ (donde $m_{\text{total}}$ es la masa total y $M$ la masa molar):

$$
p V = \frac{m_{\text{total}}}{M} R T
$$

### 2.2 Densidad de un Gas Ideal
Reorganizando la relación entre masa y volumen ($\rho = \frac{m_{\text{total}}}{V}$):

$$
\rho = \frac{p M}{R T}
$$

### 2.3 Proceso para Cantidad de Masa Constante ($n = \text{constante}$)

$$
\frac{p_1 V_1}{T_1} = \frac{p_2 V_2}{T_2}
$$

---

## 3. Coeficientes Termodinámicos: Dilatación y Compresibilidad

El cambio infinitesimal de volumen $dV$ en función de la temperatura y la presión está determinado por la diferencial total:

$$
dV = \left(\frac{\partial V}{\partial T}\right)_p dT + \left(\frac{\partial V}{\partial p}\right)_T dp
$$

### 3.1 Coeficiente de Dilatación Volumétrica ($\beta$)
Mide la variación relativa de volumen ante un cambio de temperatura a presión constante:

$$
\beta = \frac{1}{V} \left(\frac{\partial V}{\partial T}\right)_p
$$

Para un **gas ideal**:

$$
V = \frac{n R T}{p} \implies \left(\frac{\partial V}{\partial T}\right)_p = \frac{n R}{p}
$$

$$
\beta = \frac{1}{V} \left(\frac{n R}{p}\right) = \frac{1}{T}
$$

### 3.2 Compresibilidad Isotérmica ($\kappa$)
Mide la variación relativa del volumen con respecto a la presión a temperatura constante. Lleva un signo negativo debido a que el volumen disminuye al aumentar la presión ($dp > 0 \implies dV < 0$):

$$
\kappa = -\frac{1}{V} \left(\frac{\partial V}{\partial p}\right)_T
$$

Para un **gas ideal**:

$$
V = n R T p^{-1} \implies \left(\frac{\partial V}{\partial p}\right)_T = -\frac{n R T}{p^2}
$$

$$
\kappa = -\frac{1}{V} \left(-\frac{n R T}{p^2}\right) = \frac{1}{p}
$$

### 3.3 Relación Diferencial para Volúmenes
Sustituyendo $\beta$ y $\kappa$:

$$
dV = \beta V dT - \kappa V dp \implies \frac{dV}{V} = \beta dT - \kappa dp
$$

---

## 4. Modelo Cinético-Molecular del Gas Ideal

### 4.1 Supuestos del Modelo
1. El recipiente contiene $N$ moléculas idénticas de masa $m$.
2. Las moléculas son partículas puntuales (su tamaño es despreciable comparado con la distancia entre ellas).
3. Están en movimiento aleatorio continuo y obedecen las leyes de Newton.
4. Las colisiones entre moléculas y con las paredes son perfectamente elásticas.
5. Las paredes son rígidas e inmóviles.

### 4.2 Origen Microscópico de la Presión
En cada choque elástico con una pared perpendicular al eje $x$, la componente normal de la velocidad se invierte: $v_{2x} = -v_{1x}$, de modo que el cambio de cantidad de movimiento es:

$$
\Delta p_x = m v_x - (-m v_x) = 2 m v_x
$$

El número de colisiones contra un área $A$ en un tiempo $dt$ dentro de un volumen $A v_x dt$ (considerando que en promedio la mitad se mueve hacia la pared) es:

$$
\text{Choques} = \frac{1}{2} \left(\frac{N}{V}\right) A v_x dt
$$

La fuerza resultante sobre el área $A$ es:

$$
F = \frac{d p_x}{dt} = \frac{N A m v_x^2}{V} \implies p = \frac{F}{A} = \frac{N m (v_x^2)_{\text{med}}}{V}
$$

Dado que el movimiento es isotrópico: $(v_x^2)_{\text{med}} = (v_y^2)_{\text{med}} = (v_z^2)_{\text{med}} = \frac{1}{3} (v^2)_{\text{med}}$.

Sustituyendo la velocidad cuadrática media:

$$
p V = \frac{1}{3} N m (v^2)_{\text{med}} = \frac{2}{3} N \left[ \frac{1}{2} m (v^2)_{\text{med}} \right] = \frac{2}{3} K_{\text{tr}}
$$

Donde $K_{\text{tr}}$ es la energía cinética de traslación total del gas.

---

## 5. Interpretación Microscópica de la Temperatura

Al equiparar la presión cinética con la ecuación del gas ideal ($p V = n R T$):

$$
K_{\text{tr}} = \frac{3}{2} n R T
$$

### 5.1 Energía Cinética Media por Molécula
Dividiendo entre el número total de moléculas $N = n N_A$:

$$
\frac{K_{\text{tr}}}{N} = \frac{1}{2} m (v^2)_{\text{med}} = \frac{3}{2} \left(\frac{R}{N_A}\right) T = \frac{3}{2} k T
$$

Donde $k$ es la **Constante de Boltzmann**:

$$
k = \frac{R}{N_A} \approx 1,381 \times 10^{-23} \, \text{J/K}
$$

### 5.2 Ecuación de Estado en Función de la Constante de Boltzmann

$$
p V = N k T
$$

### 5.3 Rapidez Cuadrática Media (o Rapidez rms)

$$
v_{\text{rms}} = \sqrt{(v^2)_{\text{med}}} = \sqrt{\frac{3 k T}{m}} = \sqrt{\frac{3 R T}{M}}
$$

*(A una misma temperatura $T$, las moléculas con mayor masa molar $M$ poseen una menor rapidez cuadrática media).*

---

## Tabla Resumen de Fórmulas de la Unidad II

| Nombre | Fórmula Matemática | Descripción |
| ----- | ----- | ----- |
| **Ecuación de Estado (Gas Ideal - Moles)** | $p V = n R T$ | Relación macroscópica de estado para gases ideales a bajas presiones. |
| **Ecuación de Estado (Gas Ideal - Masa)** | $p V = \frac{m_{\text{total}}}{M} R T$ | Ecuación del gas ideal expresada en función de la masa total y la masa molar. |
| **Densidad del Gas Ideal** | $\rho = \frac{p M}{R T}$ | Densidad de un gas ideal calculada a partir de su presión, masa molar y temperatura. |
| **Relación de Estados ($n$ constante)** | $\frac{p_1 V_1}{T_1} = \frac{p_2 V_2}{T_2}$ | Comparación de dos estados termodinámicos cuando la masa permanece fija. |
| **Coeficiente de Dilatación Volumétrica** | $\beta = \frac{1}{V} \left(\frac{\partial V}{\partial T}\right)_p$ | Medida del cambio relativo de volumen por cambio unitario de temperatura a $p$ constante. |
| **Dilatación Volumétrica (Gas Ideal)** | $\beta = \frac{1}{T}$ | Coeficiente de dilatación volumétrica específico para un gas ideal. |
| **Compresibilidad Isotérmica** | $\kappa = -\frac{1}{V} \left(\frac{\partial V}{\partial p}\right)_T$ | Medida del cambio relativo de volumen ante variaciones de presión a $T$ constante. |
| **Compresibilidad Isotérmica (Gas Ideal)** | $\kappa = \frac{1}{p}$ | Coeficiente de compresibilidad isotérmica específico para un gas ideal. |
| **Diferencial de Volumen** | $dV = \beta V dT - \kappa V dp$ | Variación total infinitesimal de volumen en términos de $\beta$ y $\kappa$. |
| **Presión Cinetico-Molecular** | $p = \frac{1}{3} \frac{N m (v^2)_{\text{med}}}{V}$ | Presión microscópica producida por colisiones elásticas moleculares sobre las paredes. |
| **Energía Cinética de Traslación Total** | $K_{\text{tr}} = \frac{3}{2} n R T$ | Energía cinética aleatoria total acumulada por las $N$ moléculas del gas. |
| **Energía Cinética Molecular Media** | $\frac{1}{2} m (v^2)_{\text{med}} = \frac{3}{2} k T$ | Energía cinética de traslación promedio de una sola molécula en función de la temperatura. |
| **Constante de Boltzmann** | $k = \frac{R}{N_A}$ | Relación entre la constante universal de los gases $R$ y el número de Avogadro $N_A$. |
| **Ecuación de Estado (N de Moléculas)** | $p V = N k T$ | Formulación alternativa de la ecuación de estado a nivel microscópico/molecular. |
| **Rapidez Cuadrática Media ($v_{\text{rms}}$)** | $v_{\text{rms}} = \sqrt{\frac{3 R T}{M}} = \sqrt{\frac{3 k T}{m}}$ | Velocidad cuadrática media de las partículas del gas según la temperatura y la masa molar. |
