# Unidad III: Calor y Primer Principio de la Termodinámica

## 1. El Calor y la Calorimetría

### 1.1 Naturaleza del Calor
El **calor ($Q$)** es la energía en tránsito que se transfiere entre un sistema y su entorno debido únicamente a una diferencia de temperatura. El calor fluye espontáneamente desde el cuerpo de mayor temperatura hacia el de menor temperatura hasta alcanzar el **equilibrio térmico**.

* **Equivalente Mecánico del Calor:**
  $$1\text{ cal} \approx 4{,}186\text{ J}$$
  $$1\text{ BTU} = 252\text{ cal} \approx 1055\text{ J}$$

---

### 1.2 Capacidad Calorífica y Calor Específico
La cantidad de calor necesaria para modificar la temperatura de un cuerpo depende de su masa, del material y de la variación de temperatura.

* **Calor Sensible:**
  $$Q = m \, c \, \Delta T$$
  * $m$: masa $[\text{kg}]$ o $[\text{g}]$
  * $c$: calor específico del material $\left[\frac{\text{J}}{\text{kg}\cdot\text{K}}\right]$ o $\left[\frac{\text{cal}}{\text{g}\cdot^\circ\text{C}}\right]$
  * $\Delta T = T - T_0$: variación de temperatura $[\text{K}]$ o $[^\circ\text{C}]$

* **Criterio de Signos:**
  * $Q > 0$: El sistema gana/absorbe calor (se calienta).
  * $Q < 0$: El sistema cede/pierde calor (se enfría).
  * $Q = 0$: Proceso adiabático (sin intercambio de calor).

* **Capacidad Calorífica ($C$):**
  $$C = m \, c$$

* **Capacidad Calorífica Molar ($C_m$):**
  $$Q = n \, C_m \, \Delta T$$
  * $n$: número de moles $[\text{mol}]$
  * $C_m$: capacidad calorífica molar $\left[\frac{\text{J}}{\text{mol}\cdot\text{K}}\right]$

---

### 1.3 Calorimetría y Cambios de Fase
Durante un cambio de fase (fusión, solidificación, vaporización, condensación), la transferencia de calor produce una reestructuración molecular a temperatura constante.

* **Calor Latente ($L$):**
  $$Q = \pm m \, L$$
  * Usar signó positivo ($+$) para absorción de calor (fusión, vaporización).
  * Usar signo negativo ($-$) para liberación de calor (solidificación, condensación).

* **Valores notables para el Agua:**
  * Calor latente de fusión ($L_f$): $3{,}34 \times 10^5\text{ J/kg} \approx 79{,}6\text{ cal/g}$
  * Calor latente de vaporización ($L_v$): $2{,}256 \times 10^6\text{ J/kg} \approx 539\text{ cal/g}$

---

## 2. Mecanismos de Transferencia de Calor

La tasa a la cual se transfiere calor por unidad de tiempo se conoce como **Corriente de Calor ($H$)** o flujo térmico:
$$H = \frac{\mathrm{d}Q}{\mathrm{d}t} \quad \text{o} \quad H = \frac{Q}{\Delta t} \quad [\text{Watt (W)} = \text{J/s}]$$

### 2.1 Conducción
Transferencia de energía a nivel atómico/molecular por contacto directo, sin transporte neto de materia.

* **Ley de Conducción (Fourier):**
  $$H = k \, A \, \frac{T_C - T_F}{L}$$
  * $k$: conductividad térmica del material $\left[\frac{\text{W}}{\text{m}\cdot\text{K}}\right]$
  * $A$: área de la sección transversal $[\text{m}^2]$
  * $L$: longitud o espesor del conductor $[\text{m}]$
  * $T_C, T_F$: temperaturas del extremo caliente y frío respectivamente $[\text{K}]$ o $[^\circ\text{C}]$

* **Gradiente Térmico:**
  $$\text{Gradiente} = \frac{T_C - T_F}{L}$$

* **Resistencia Térmica ($R$):**
  $$R = \frac{L}{k} \implies H = \frac{A (T_C - T_F)}{R}$$

* **Asociación de Conductores (Barras/Paredes):**
  * **En Serie:** La corriente de calor es uniforme y las resistencias se suman.
    $$H_{\text{total}} = H_1 = H_2$$
    $$R_{\text{total}} = R_1 + R_2 + \dots + R_n$$
  * **En Paralelo:** La corriente total es la suma de las corrientes individuales.
    $$H_{\text{total}} = H_1 + H_2 + \dots + H_n$$
    $$\frac{1}{R_{\text{total}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n}$$

---

### 2.2 Convección
Transferencia de calor producida por el movimiento masivo de un fluido (líquido o gas).
* **Convección Natural:** Se genera espontáneamente por variaciones de densidad térmicas.
* **Convección Forzada:** Impulsada mecánicamente (bombas, ventiladores).

* **Ley de Enfriamiento de Newton:**
  $$H = h \, A \, (T_s - T_f)$$
  * $h$: coeficiente de transferencia por convección $\left[\frac{\text{W}}{\text{m}^2\cdot\text{K}}\right]$
  * $T_s$: temperatura superficial
  * $T_f$: temperatura del fluido alejado

---

### 2.3 Radiación
Transferencia mediante ondas electromagnéticas. No requiere un medio material para propagarse (ocurre en el vacío).

* **Ley de Stefan-Boltzmann:**
  $$H = \sigma \, e \, A \, T^4$$
  * $\sigma = 5{,}6704 \times 10^{-8}\frac{\text{W}}{\text{m}^2\cdot\text{K}^4}$ (Constante de Stefan-Boltzmann)
  * $e$: emisividad ($0 \le e \le 1$). Para un *cuerpo negro*, $e = 1$.
  * $T$: Temperatura absoluta **estrictamente en Kelvin (K)**.

* **Radiación Neta (Intercambio con el Entorno):**
  $$H_{\text{neta}} = \sigma \, e \, A \, (T^4 - T_{\text{entorno}}^4)$$

---

## 3. Trabajo Termodinámico y Energía Interna

### 3.1 Trabajo Mecánico ($W$)
Trabajo realizado por un gas durante un proceso de frontera móvil en cuasiequilibrio:

$$W = \int_{V_1}^{V_2} p \, \mathrm{d}V$$

* **Convenio de Signos:**
  * $W > 0$: Expansión ($\Delta V > 0$). El gas realiza trabajo sobre el entorno.
  * $W < 0$: Compresión ($\Delta V < 0$). El entorno realiza trabajo sobre el gas.
  * $W = 0$: Isochórico/Isovolumétrico ($\Delta V = 0$).

* **Casos Particulares:**
  * **Proceso Isobárico ($p = \text{cte}$):**
    $$W = p \, (V_2 - V_1)$$
  * **Proceso Isotérmico (Gas Ideal, $T = \text{cte}$):**
    $$W = n \, R \, T \, \ln\left(\frac{V_2}{V_1}\right)$$

---

### 3.2 Energía Interna ($U$)
Suma total de la energía cinética y potencial microscópica de las moléculas constituyentes del sistema.

* **Para un Gas Ideal:** La energía interna depende **únicamente de la temperatura**:
  $$U = \frac{3}{2} n \, R \, T \quad \text{(Monoatómico)}$$
  $$\Delta U = n \, C_V \, \Delta T$$

---

## 4. Primer Principio de la Termodinámica

Representa la ley general de conservación de la energía aplicada a sistemas termodinámicos.

* **Forma Integral:**
  $$\Delta U = Q - W$$

* **Forma Diferencial:**
  $$\mathrm{d}U = \delta Q - \delta W$$

  * $\Delta U$ ($\mathrm{d}U$): Función de estado; independiente de la trayectoria (diferencial exacta).
  * $Q$ y $W$ ($\delta Q, \delta W$): Funciones de trayectoria; dependen del camino recorrido (diferenciales inexactas).

---

## 5. Tabla Resumen de Fórmulas

| Nombre de la Fórmula | Fórmula | Descripción |
| :--- | :--- | :--- |
| **Calor Sensible** | $Q = m \, c \, \Delta T$ | Calor intercambiado que genera variación de temperatura sin cambio de fase. |
| **Capacidad Calorífica** | $C = m \, c$ | Capacidad de un cuerpo completo para almacenar calor por unidad de temperatura. |
| **Calor Molar** | $Q = n \, C_m \, \Delta T$ | Calor necesario para alterar la temperatura en función del número de moles. |
| **Calor Latente** | $Q = \pm m \, L$ | Calor intercambiado durante una transición de fase a temperatura constante. |
| **Corriente de Calor** | $H = \frac{Q}{\Delta t}$ | Tasa de transferencia de calor por unidad de tiempo. |
| **Conducción Térmica (Fourier)** | $H = k A \frac{T_C - T_F}{L}$ | Tasa de calor transferido por conducción en materiales sólidos. |
| **Resistencia Térmica** | $R = \frac{L}{k}$ | Oposición del material al flujo de calor por conducción. |
| **Convección (Newton)** | $H = h A (T_s - T_f)$ | Transferencia de calor entre una superficie sólida y un fluido en movimiento. |
| **Radiación (Stefan-Boltzmann)** | $H = \sigma e A T^4$ | Potencia térmica emitida electromagnéticamente por un cuerpo a temperatura $T$. |
| **Radiación Neta** | $H_{\text{neta}} = \sigma e A (T^4 - T_{\text{entorno}}^4)$ | Tasa neta de calor intercambiado por radiación entre un cuerpo y su entorno. |
| **Trabajo General de un Gas** | $W = \int_{V_1}^{V_2} p \, \mathrm{d}V$ | Trabajo termodinámico debido al cambio de volumen de un gas. |
| **Trabajo Isobárico** | $W = p (V_2 - V_1)$ | Trabajo mecánico en un proceso a presión constante. |
| **Trabajo Isotérmico** | $W = n R T \ln\left(\frac{V_2}{V_1}\right)$ | Trabajo realizado por un gas ideal a temperatura constante. |
| **Energía Interna (Gas Ideal)** | $\Delta U = n C_V \Delta T$ | Variación de la energía microscópica total del sistema en función de $\Delta T$. |
| **Primer Principio de la Termodinámica** | $\Delta U = Q - W$ | Principio de conservación de energía entre calor, trabajo y energía interna. |