# Unidad II: Ecuación de Estado y Teoría Cinético-Molecular

## 1. Conceptos Fundamentales de Sistemas Termodinámicos

* **Sistema Termodinámico:** Porción del universo delimitada por fronteras reales o imaginarias que se aisla para su estudio.
  * **Sistema Cerrado:** Intercambia energía pero no materia con el entorno.
  * **Sistema Abierto:** Intercambia energía y materia con el entorno.
  * **Sistema Aislado:** No intercambia ni energía ni materia con su entorno.
* **Estado de un Sistema:** Condición macroscópica definida por el valor numérico de sus variables de estado (presión $p$, volumen $V$, temperatura $T$, masa $m$ o moles $n$).
* **Proceso o Transformación Termodinámica:** Cambio de un estado de equilibrio a otro mediante la variación de una o más variables.
  * **Proceso Cuasiestático:** Ocurre tan lentamente que el sistema pasa por una sucesión de estados infinitamente cercanos al equilibrio.
  * **Proceso Reversible:** Aquel cuyo sentido puede invertirse mediante un cambio infinitesimal en las condiciones del entorno. Todo proceso reversible es necesariamente cuasiestático.
  * **Proceso Irreversible:** Transformación real producida por diferencias finitas en las propiedades del sistema.

### Clasificación de Procesos por Variable Constante
* **Isotérmico:** Temperatura constante ($\Delta T = 0$).
* **Isobárico:** Presión constante ($\Delta p = 0$).
* **Isocórico / Isométrico:** Volumen constante ($\Delta V = 0$).
* **Adiabático:** Sin transferencia de calor con el entorno ($Q = 0$).

---

## 2. Ecuación de Estado del Gas Ideal

### 2.1 Variables y Constantes
La relación macroscópica entre las variables de estado de un gas ideal está dada por:

$$p V = n R T$$

Donde:
* $p$: Presión absoluta $[\text{Pa}]$ o $[\text{atm}]$
* $V$: Volumen del recipiente $[\text{m}^3]$ o $[\text{L}]$
* $n$: Número de moles $[\text{mol}]$, donde $n = \frac{m_{\text{total}}}{M}$ ($M$ = masa molar $[\text{g/mol}]$)
* $T$: Temperatura absoluta **estrictamente en Kelvin** ($T[\text{K}] = t[^\circ\text{C}] + 273{,}15$)
* $R$: Constante universal de los gases ideales:
  $$R = 8{,}3145 \text{ J/(mol}\cdot\text{K)}$$
  $$R = 0{,}08206 \text{ L}\cdot\text{atm/(mol}\cdot\text{K)}$$

### 2.2 Formas Alternativas de la Ecuación de Estado
* **En función del número total de moléculas ($N$):**
  $$p V = N k T$$
  Donde $k = \frac{R}{N_A} = 1{,}381 \times 10^{-23} \text{ J/K}$ es la **Constante de Boltzmann** y $N_A = 6{,}022 \times 10^{23} \text{ mol}^{-1}$ es el número de Avogadro.

* **Densidad de un Gas Ideal ($\rho$):**
  $$\rho = \frac{p M}{R T}$$

* **Relación de Estados para Masa Constante ($n = \text{constante}$):**
  $$\frac{p_1 V_1}{T_1} = \frac{p_2 V_2}{T_2}$$

---

## 3. Modelo Cinético-Molecular del Gas Ideal

### 3.1 Postulados del Modelo
1. El gas está compuesto por un número enorme $N$ de moléculas idénticas de masa $m$.
2. Las moléculas se comportan como masas puntuales; su volumen propio es despreciable frente al volumen total $V$.
3. Las moléculas están en movimiento continuo, aleatorio y obedecen las leyes de Newton.
4. Las colisiones entre moléculas y contra las paredes rígidas del recipiente son **perfectamente elásticas**.
5. No existen fuerzas de atracción o repulsión intermolecular (salvo durante las colisiones breves).

### 3.2 Origen Microscópico de la Presión
Durante un choque elástico contra una pared perpendicular al eje $x$, una molécula invierte su componente de velocidad perpendicular ($v_{1x} = -|v_x| \rightarrow v_{2x} = |v_x|$), experimentando un cambio en la cantidad de movimiento:

$$\Delta P_x = 2 m |v_x|$$

Sumando los choques de todas las moléculas contenidas en un volumen cilíndrico $A |v_x| \mathrm{d}t$, la presión macroscópica generada sobre las paredes es:

$$p = \frac{F}{A} = \frac{N m (v_x^2)_{\text{med}}}{V}$$

Dado que el movimiento es isotrópico en tres dimensiones ($(v_x^2)_{\text{med}} = \frac{1}{3} (v^2)_{\text{med}}$):

$$p V = \frac{1}{3} N m (v^2)_{\text{med}} = \frac{2}{3} K_{\text{tr}}$$

Donde $K_{\text{tr}}$ es la energía cinética de traslación total del gas.

### 3.3 Interpretación Microscópica de la Temperatura

Al comparar la ecuación cinético-molecular con la ley del gas ideal ($p V = n R T$):

* **Energía Cinética de Traslación Total ($K_{\text{tr}}$):**
  $$K_{\text{tr}} = \frac{3}{2} n R T$$

* **Energía Cinética Media por Molécula:**
  $$\bar{E}_k = \frac{1}{2} m (v^2)_{\text{med}} = \frac{3}{2} k T$$

> *La energía cinética promedio de una molécula depende **exclusivamente** de la temperatura absoluta $T$ y es independiente de la masa o tipo de molécula.*

### 3.4 Rapidez Cuadrática Media / Eficaz ($v_{\text{rms}}$)
La rapidez eficaz o cuadrática media representa la velocidad promedio del conjunto molecular:

$$v_{\text{rms}} = \sqrt{(v^2)_{\text{med}}} = \sqrt{\frac{3 k T}{m}} = \sqrt{\frac{3 R T}{M}}$$

---

## 4. Coeficientes de Dilatación Térmica y Compresibilidad

Dado un sistema pVT cuya relación diferencial es:

$$\mathrm{d}V = \left(\frac{\partial V}{\partial T}\right)_p \mathrm{d}T + \left(\frac{\partial V}{\partial p}\right)_T \mathrm{d}p$$

### 4.1 Coeficiente de Dilatación Volumétrica ($\beta$)
Mide la variación relativa del volumen respecto a la temperatura a presión constante:

$$\beta = \frac{1}{V} \left(\frac{\partial V}{\partial T}\right)_p$$

* **Para un Gas Ideal:**
  $$\beta = \frac{1}{T} \quad [\text{K}^{-1}]$$

### 4.2 Compresibilidad Isotérmica ($\kappa$)
Mide la variación relativa del volumen respecto a la presión a temperatura constante (el signo negativo asegura un valor positivo):

$$\kappa = -\frac{1}{V} \left(\frac{\partial V}{\partial p}\right)_T$$

* **Para un Gas Ideal:**
  $$\kappa = \frac{1}{p} \quad [\text{Pa}^{-1}]$$

* **Ecuación Diferencial del Volumen:**
  $$\mathrm{d}V = \beta V \mathrm{d}T - \kappa V \mathrm{d}p \implies \frac{\mathrm{d}V}{V} = \beta \mathrm{d}T - \kappa \mathrm{d}p$$

---

## 5. Tabla Resumen de Fórmulas

| Nombre de la Fórmula | Fórmula | Descripción |
| ----- | ----- | ----- |
| **Ecuación del Gas Ideal** | $p V = n R T$ | Relación de estado macroscópica para gases ideales a bajas presiones y altas temperaturas. |
| **Forma Molecular del Gas Ideal** | $p V = N k T$ | Ecuación de estado en función del número total de moléculas y la constante de Boltzmann. |
| **Densidad de un Gas Ideal** | $\rho = \frac{p M}{R T}$ | Densidad de un gas en función de su presión, temperatura y masa molar. |
| **Relación de Estados (Masa Constante)** | $\frac{p_1 V_1}{T_1} = \frac{p_2 V_2}{T_2}$ | Comparación entre dos estados de equilibrio de una misma masa de gas. |
| **Presión Cinético-Molecular** | $p = \frac{N m (v_x^2)_{\text{med}}}{V}$ | Origen microscópico de la presión por choque elástico de moléculas. |
| **Energía Cinética Total ($K_{\text{tr}}$)** | $K_{\text{tr}} = \frac{3}{2} n R T$ | Energía cinética aleatoria de traslación de $n$ moles de un gas ideal. |
| **Energía Cinética por Molécula** | $\bar{E}_k = \frac{3}{2} k T$ | Energía cinética de traslación media de una sola molécula en función de $T$. |
| **Rapidez Eficaz ($v_{\text{rms}}$)** | $v_{\text{rms}} = \sqrt{\frac{3 R T}{M}}$ | Velocidad cuadrática media de las moléculas de un gas. |
| **Constante de Boltzmann** | $k = \frac{R}{N_A}$ | Relación entre la constante universal de los gases y el número de Avogadro. |
| **Coeficiente de Dilatación Volumétrica** | $\beta = \frac{1}{V} \left(\frac{\partial V}{\partial T}\right)_p$ | Tasa de cambio de volumen por unidad de grado térmico a presión constante. |
| **Dilatación Volumétrica (Gas Ideal)** | $\beta = \frac{1}{T}$ | Coeficiente de dilatación volumétrica específico para gases ideales. |
| **Compresibilidad Isotérmica** | $\kappa = -\frac{1}{V} \left(\frac{\partial V}{\partial p}\right)_T$ | Cambio relativo del volumen al variar la presión a temperatura constante. |
| **Compresibilidad (Gas Ideal)** | $\kappa = \frac{1}{p}$ | Compresibilidad isotérmica específica para gases ideales. |
| **Diferencial Total del Volumen** | $\frac{\mathrm{d}V}{V} = \beta \mathrm{d}T - \kappa \mathrm{d}p$ | Expresión diferencial del cambio de volumen en función de $\beta$ y $\kappa$. |