# Conceptos y Fórmulas de Termodinámica y Estado de los Gases

---

## 1. Consecuencias del Primer Principio de la Termodinámica

### Proceso Adiabático
Un proceso termodinámico en el cual **no hay transferencia de calor** entre el sistema y su entorno ($Q = 0$).

$$\Delta U = -W$$

* **Variables de Estado en Procesos Adiabáticos (Gas Ideal):**
  $$T V^{\gamma - 1} = \text{Constante}$$
  $$p V^{\gamma} = \text{Constante}$$

* **Trabajo en un Proceso Adiabático ($W$):**
  $$W = -n c_V (T_2 - T_1) = \frac{1}{\gamma - 1} (p_1 V_1 - p_2 V_2)$$

* **Coeficiente de Capacidad Calorífica ($\gamma$):** Relación entre las capacidades caloríficas a presión constante ($C_p$) y volumen constante ($C_V$).
  $$\gamma = \frac{C_p}{C_V}$$
  * **Gases monoatómicos:** $\gamma = \frac{5}{3} \approx 1{,}67$
  * **Gases diatómicos:** $\gamma = \frac{7}{5} = 1{,}4$

---

### Máquinas Térmicas
Dispositivos que transforman parcialmente la energía térmica (calor) proveniente de una fuente caliente en trabajo mecánico, expulsando el calor remanente a una fuente fría.

* **Trabajo Realizado ($W$):**
  $$W = Q_C - Q_F$$
  * $Q_C$: Calor absorbido del foco caliente.
  * $Q_F$: Calor cedido al foco frío.

* **Eficiencia Térmica ($e$):** Proporción del calor absorbido que se convierte efectivamente en trabajo.
  $$e = \frac{W}{Q_C} = \frac{Q_C - Q_F}{Q_C} = 1 - \frac{Q_F}{Q_C}$$

---

### Refrigeradores
Máquinas térmicas que operan en sentido inverso: consumen trabajo externo para extraer calor de una fuente fría y cederlo a una fuente caliente.

* **Coeficiente de Rendimiento ($K$ o $COP$):** Relación entre el calor extraído del foco frío y el trabajo consumido.
  $$K = \frac{Q_F}{W} = \frac{Q_F}{Q_C - Q_F}$$

---

### Ciclo de Carnot
Ciclo termodinámico teórico compuesto por cuatro procesos reversibles que logra la máxima eficiencia posible entre dos temperaturas fijas ($T_C$ y $T_F$):
1. **Expansión isotérmica reversible** a temperatura $T_C$ ($Q_C$ absorbido).
2. **Expansión adiabática reversible** (la temperatura disminuye de $T_C$ a $T_F$).
3. **Compresión isotérmica reversible** a temperatura $T_F$ ($Q_F$ expulsado).
4. **Compresión adiabática reversible** (retorno al estado inicial).

* **Relación de Calor y Temperatura en Carnot:**
  $$\frac{Q_C}{Q_F} = \frac{T_C}{T_F}$$

* **Eficiencia de la Máquina de Carnot ($e_{\text{Carnot}}$):**
  $$e_{\text{Carnot}} = 1 - \frac{T_F}{T_C}$$

* **Rendimiento del Refrigerador de Carnot ($K_{\text{Carnot}}$):**
  $$K_{\text{Carnot}} = \frac{T_F}{T_C - T_F}$$

---

## 2. Entalpía y Ecuaciones Independientes de Estado

### Entalpía ($H$)
Función de estado definida para facilitar el análisis energético en procesos a presión constante. Representa el contenido calórico total de un sistema.

$$H = U + pV$$

* **Cambio de Entalpía ($\Delta H$):**
  $$\Delta H = \Delta U + \Delta(pV)$$

* **A presión constante ($\Delta p = 0$):**
  $$\Delta H = Q_p$$

---

### Capacidades Caloríficas

* **A volumen constante ($C_V$):**
  $$C_V = \left(\frac{\partial U}{\partial T}\right)_V$$

* **A presión constante ($C_p$):**
  $$C_p = \left(\frac{\partial H}{\partial T}\right)_p$$

* **Relación de Mayer (Gases Ideales):**
  $$C_p - C_V = R \quad \text{o bien} \quad c_p - c_V = R$$

---

### Ecuación General de Cambio de Energía Interna y Entalpía

$$\mathrm{d}U = C_V \mathrm{d}T + \left[ T \left(\frac{\partial p}{\partial T}\right)_V - p \right] \mathrm{d}V$$

$$\mathrm{d}H = C_p \mathrm{d}T + \left[ V - T \left(\frac{\partial V}{\partial T}\right)_p \right] \mathrm{d}p$$

---

### Coeficientes Termodinámicos de Derivada Parcial

* **Coeficiente de Expansión Isobárica ($\alpha$):** Fracción de cambio de volumen por grado de cambio térmico a presión constante.
  $$\alpha = \frac{1}{V} \left(\frac{\partial V}{\partial T}\right)_p$$

* **Compresibilidad Isotérmica ($\kappa_T$):** Cambio relativo de volumen con la presión a temperatura constante.
  $$\kappa_T = -\frac{1}{V} \left(\frac{\partial V}{\partial p}\right)_T$$

* **Relación de Capacidades Caloríficas Generales:**
  $$C_p - C_V = \frac{T V \alpha^2}{\kappa_T}$$

---

### Coeficiente de Joule-Thomson ($\mu_{JT}$)
Representa la variación de temperatura que experimenta un gas al expandirse a través de un estrangulamiento o tapón poroso a entalpía constante ($\Delta H = 0$).

$$\mu_{JT} = \left(\frac{\partial T}{\partial p}\right)_H = \frac{T \left(\frac{\partial V}{\partial T}\right)_p - V}{C_p} = \frac{V (\alpha T - 1)}{C_p}$$

* **En un Gas Ideal:** $\alpha = \frac{1}{T}$, por lo tanto $\mu_{JT} = 0$ (no ocurre cambio de temperatura al expandirse a entalpía constante).