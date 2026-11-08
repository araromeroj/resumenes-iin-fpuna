# Unidad IV: Algunas Consecuencias del Primer Principio de la Termodinámica

---

## 1. Introducción y Relaciones Termodinámicas Fundamentales

El Primer Principio de la Termodinámica establece el principio de conservación de la energía para sistemas termodinámicos:

$$dU = dQ - dW$$

Donde $dU$ es el diferencial de la energía interna, $dQ$ es el calor intercambiado por el sistema y $dW$ es el trabajo realizado por el sistema. Para un sistema simple $PVT$ cuyo trabajo es únicamente de expansión p-V, se tiene $dW = P \, dV$.

El estado de una sustancia pura se determina completamente mediante dos variables independientes cualesquiera entre $P$, $V$ y $T$. La energía interna $U$ (o específica $u$) y la entalpía $H$ (o específica $h$) son funciones de estado.

---

## 2. Derivación de Relaciones con Variables Independientes

### 2.1. Temperatura ($T$) y Volumen específico ($v$) Independientes

Considerando $u = u(T, v)$, su diferencial total expresado con derivadas parciales es:

$$du = \left( \frac{\partial u}{\partial T} \right)_v dT + \left( \frac{\partial u}{\partial v} \right)_T dv$$

Sustituyendo $du$ en el Primer Principio ($dQ = du + P \, dv$):

$$dQ = \left( \frac{\partial u}{\partial T} \right)_v dT + \left[ \left( \frac{\partial u}{\partial v} \right)_T + P \right] dv$$

- **Proceso a volumen constante ($dv = 0$):**
  $$dQ = \left( \frac{\partial u}{\partial T} \right)_v dT$$
  
  Definiendo la capacidad calorífica a volumen constante $C_v$ (o molar $C_v = \frac{1}{n}\frac{dQ}{dT}$):
  
  $$C_v = \left( \frac{\partial u}{\partial T} \right)_v$$

Esto demuestra que la capacidad calorífica a volumen constante es directamente la derivada parcial de la energía interna respecto a la temperatura a volumen constante.

---

### 2.2. Temperatura ($T$) y Presión ($P$) Independientes

Considerando la entalpía por unidad de masa $h = h(T, P)$, su diferencial total es:

$$dh = \left( \frac{\partial h}{\partial T} \right)_P dT + \left( \frac{\partial h}{\partial P} \right)_T dP$$

A partir de la definición de entalpía $h = u + Pv$, tenemos $dh = du + P \, dv + v \, dP$. Como $dQ = du + P \, dv$, sustituyendo obtenemos:

$$dQ = dh - v \, dP$$

Reemplazando el diferencial de entalpía:

$$dQ = \left( \frac{\partial h}{\partial T} \right)_P dT + \left[ \left( \frac{\partial h}{\partial P} \right)_T - v \right] dP$$

- **Proceso a presión constante ($dP = 0$):**
  $$dQ = \left( \frac{\partial h}{\partial T} \right)_P dT$$
  
  Definiendo la capacidad calorífica a presión constante $C_p$:
  
  $$C_p = \left( \frac{\partial h}{\partial T} \right)_P$$

---

## 3. Entalpía

La entalpía es una función de estado macroscópica definida operacionalmente como:

$$H = U + PV$$

O en términos molares/específicos:

$$h = u + Pv$$

### Propiedades y Significado Físico:
1. **Función de Estado:** Su valor depende exclusivamente del estado actual del sistema, no del camino seguido.
2. **Procesos Isobáricos:** En una transformación a presión constante donde solo hay trabajo de expansión $P \, dV$:
   $$Q_P = \Delta H$$
   El calor transferido a presión constante equivale exactamente a la variación de entalpía del sistema.

---

## 4. Experimentos Fundamentales

### 4.1. Experimento de Joule (Expansión Libre)
Joule conectó dos recipientes rígidos sumergidos en un baño de agua. Un recipiente contenía un gas y el otro estaba evacuado (vacío). Al abrir la llave de paso, el gas se expandió libremente en el vacío.

- **Resultados del experimento:**
  - Trabajo realizado: $W = 0$ (expandió contra presión exterior nula).
  - Calor intercambiado: $Q = 0$ (la temperatura del baño de agua no varió, $\Delta T_{agua} = 0$).
  - Por la primera ley: $\Delta U = Q - W = 0$.

De la diferencial de $u(T,v)$:

$$du = \left( \frac{\partial u}{\partial T} \right)_v dT + \left( \frac{\partial u}{\partial v} \right)_T dv = 0$$

Dado que $dT = 0$ para un gas ideal durante la expansión libre, se concluye experimentalmente que para un **gas ideal**:

$$\left( \frac{\partial u}{\partial v} \right)_T = 0 \quad \implies \quad u = u(T)$$

La energía interna de un gas ideal depende **únicamente** de la temperatura.

---

### 4.2. Experimento de Joule-Kelvin (Efecto Joule-Thomson o Tabique Poroso)
Consiste en el flujo continuo de un gas a través de un tapón poroso o válvula de estrangulamiento térmicamente aislada, pasando de una región de alta presión $P_1$ a una de baja presión $P_2$.

- **Análisis termodinámico:**
  - Trabajo de entrada sobre el gas: $W_1 = -P_1 V_1$.
  - Trabajo de salida del gas: $W_2 = P_2 V_2$.
  - Trabajo neto: $W = P_2 V_2 - P_1 V_1$.
  - Como el conducto es adiabático: $Q = 0$.
  - Aplicando el primer principio: $\Delta U = U_2 - U_1 = -W = P_1 V_1 - P_2 V_2$.
  - Reagrupando términos:
    $$U_1 + P_1 V_1 = U_2 + P_2 V_2 \quad \implies \quad H_1 = H_2$$

El proceso de estrangulamiento es un **proceso isoentálpico** ($\Delta H = 0$).

- **Coeficiente de Joule-Thomson ($\mu_{JT}$):**
  $$\mu_{JT} = \left( \frac{\partial T}{\partial P} \right)_H$$
  - Si $\mu_{JT} > 0$: El gas se enfría al expandirse.
  - Si $\mu_{JT} < 0$: El gas se calienta al expandirse.
  - Para un **gas ideal**: $\mu_{JT} = 0$ (no hay cambio de temperatura).

---

## 5. Capacidades Caloríficas en Gases Ideales

### 5.1. Diferencia entre Capacidades Caloríficas (Relación de Mayer)
Para un gas ideal $u = u(T)$ y $Pv = RT$. La entalpía específica es:

$$h = u + RT$$

Derivando respecto a $T$:

$$\frac{dh}{dT} = \frac{du}{dT} + R$$

Como $C_p = \frac{dh}{dT}$ y $C_v = \frac{du}{dT}$ para un gas ideal:

$$C_p - C_v = R \quad \text{(Relación molar)}$$

O en forma total para $n$ moles:

$$C_P - C_V = nR$$

---

### 5.2. Cociente entre Capacidades Caloríficas ($\gamma$)
El coeficiente adiabático o razón de calores específicos se define como:

$$\gamma = \frac{C_p}{C_v}$$

Como $C_p > C_v$, siempre se cumple que $\gamma > 1$.

- **Gas Monoatómico:** $C_v = \frac{3}{2}R$, $C_p = \frac{5}{2}R \implies \gamma = \frac{5}{3} \approx 1.67$
- **Gas Diatómico:** $C_v = \frac{5}{2}R$, $C_p = \frac{7}{2}R \implies \gamma = \frac{7}{5} = 1.40$

---

## 6. Proceso Adiabático para un Gas Ideal

En un proceso adiabático cuasiestático, no hay transferencia de calor ($dQ = 0$).

### 6.1. Relaciones entre $P$, $V$ y $T$
A partir del primer principio:

$$dU = -dW \implies n C_v dT = -P dV$$

Utilizando la ecuación de estado del gas ideal $P = \frac{nRT}{V}$ y diferenciando:

$$n C_v dT = -\frac{nRT}{V} dV \implies \frac{dT}{T} + \frac{R}{C_v} \frac{dV}{V} = 0$$

Como $\frac{R}{C_v} = \frac{C_p - C_v}{C_v} = \gamma - 1$:

$$\frac{dT}{T} + (\gamma - 1) \frac{dV}{V} = 0$$

Integrando entre dos estados:

$$T V^{\gamma - 1} = \text{constante} \quad \implies \quad T_1 V_1^{\gamma - 1} = T_2 V_2^{\gamma - 1}$$

Sustituyendo $T = \frac{PV}{nR}$:

$$P V^\gamma = \text{constante} \quad \implies \quad P_1 V_1^\gamma = P_2 V_2^\gamma$$

En función de $T$ y $P$:

$$T^\gamma P^{1-\gamma} = \text{constante} \quad \implies \quad P_1^{1-\gamma} T_1^\gamma = P_2^{1-\gamma} T_2^\gamma$$

---

### 6.2. Trabajo en un Proceso Adiabático
Como $Q = 0$, $W = -\Delta U$:

$$W = -n C_v (T_2 - T_1) = n C_v (T_1 - T_2)$$

Sustituyendo $C_v = \frac{R}{\gamma - 1}$ y $nRT = PV$:

$$W = \frac{P_1 V_1 - P_2 V_2}{\gamma - 1}$$

---

## 7. Máquinas Térmicas, Refrigeradores y Bombas de Calor

### 7.1. Máquinas Térmicas
Dispositivos que operan en ciclo extrayendo calor $Q_H$ de una fuente caliente a temperatura $T_H$, produciendo trabajo neto $W$ y rechazando un calor $Q_C$ a una fuente fría a temperatura $T_C$.

- **Primera Ley en el Ciclo ($\Delta U = 0$):**
  $$W = |Q_H| - |Q_C|$$

- **Eficiencia Térmica ($\eta$):**
  $$\eta = \frac{W}{|Q_H|} = \frac{|Q_H| - |Q_C|}{|Q_H|} = 1 - \frac{|Q_C|}{|Q_H|}$$

---

### 7.2. Refrigeradores y Bombas de Calor
Dispositivos cíclicos que absorben calor de una fuente a baja temperatura y lo descargan a una fuente a alta temperatura mediante el aporte de trabajo externo $W$.

- **Refrigerador:** Su objetivo principal es remover calor $Q_C$ de un espacio frío.
  - **Coeficiente de Rendimiento ($K$ o $COP_R$):**
    $$K = \frac{|Q_C|}{W} = \frac{|Q_C|}{|Q_H| - |Q_C|}$$

- **Bomba de Calor:** Su objetivo principal es suministrar calor $Q_H$ a un espacio caliente.
  - **Coeficiente de Rendimiento ($COP_{HP}$):**
    $$COP_{HP} = \frac{|Q_H|}{W} = \frac{|Q_H|}{|Q_H| - |Q_C|} = K + 1$$

---

## 8. Ciclos Termodinámicos

### 8.1. Ciclo de Carnot
Es el ciclo ideal reversible compuesto por cuatro procesos:
1. **1-2:** Expansión isotérmica a temperatura $T_H$ (absorbe $Q_H$).
2. **2-3:** Expansión adiabática de $T_H$ a $T_C$.
3. **3-4:** Compresión isotérmica a temperatura $T_C$ (cede $Q_C$).
4. **4-1:** Compresión adiabática de $T_C$ a $T_H$.

Para cualquier ciclo reversible operando entre dos fuentes térmicas:

$$\frac{|Q_C|}{|Q_H|} = \frac{T_C}{T_H}$$

- **Eficiencia Máxima de Carnot ($\eta_{Carnot}$):**
  $$\eta_{Carnot} = 1 - \frac{T_C}{T_H}$$

- **Coeficiente de Rendimiento del Refrigerador de Carnot ($K_{Carnot}$):**
  $$K_{Carnot} = \frac{T_C}{T_H - T_C}$$

---

### 8.2. Ciclo de Otto (Motor a Gasolina)
Modelo ideal para motores de combustión interna de encendido por chispa. Consta de:
1. **1-2:** Compresión adiabática.
2. **2-3:** Calentamiento isocórico (adición de calor $Q_H$ a volumen constante).
3. **3-4:** Expansión adiabática (carrera de potencia).
4. **4-1:** Enfriamiento isocórico (rechazo de calor $Q_C$ a volumen constante).

- **Relación de Compresión ($r$):** $r = \frac{V_{max}}{V_{min}} = \frac{V_1}{V_2}$

- **Eficiencia Térmica del Ciclo Otto:**
  $$\eta_{Otto} = 1 - \frac{1}{r^{\gamma - 1}}$$

---

### 8.3. Ciclo Diesel (Motor a Gasoil)
Modelo ideal para motores de combustión interna de encendido por compresión. Consta de:
1. **1-2:** Compresión adiabática.
2. **2-3:** Calentamiento isobárico (adición de calor $Q_H$ a presión constante).
3. **3-4:** Expansión adiabática.
4. **4-1:** Enfriamiento isocórico (rechazo de calor $Q_C$ a volumen constante).

- **Relación de Cierre de Admisión/Corte ($r_c$):** $r_c = \frac{V_3}{V_2}$

- **Eficiencia Térmica del Ciclo Diesel:**
  $$\eta_{Diesel} = 1 - \frac{1}{r^{\gamma - 1}} \left[ \frac{r_c^\gamma - 1}{\gamma (r_c - 1)} \right]$$

---

## 9. Tabla Resumen de Fórmulas de la Unidad IV

| Nombre de la Fórmula | Formulación Matemática | Descripción / Aplicación |
| :--- | :--- | :--- |
| **Primer Principio de la Termodinámica** | $dU = dQ - dW$ | Balance energético fundamental del sistema en forma diferencial. |
| **Capacidad Calorífica a Volumen Constante** | $C_v = \left(\frac{\partial u}{\partial T}\right)_v$ | Variación de la energía interna con respecto a la temperatura a volumen constante. |
| **Capacidad Calorífica a Presión Constante** | $C_p = \left(\frac{\partial h}{\partial T}\right)_P$ | Variación de la entalpía con respecto a la temperatura a presión constante. |
| **Definición de Entalpía** | $H = U + PV$ (o $h = u + Pv$) | Función de estado que representa el contenido calórico a presión constante. |
| **Relación de Mayer** | $C_p - C_v = R$ | Relación entre las capacidades caloríficas molares de un gas ideal. |
| **Coeficiente Adiabático** | $\gamma = \frac{C_p}{C_v}$ | Cociente entre las capacidades caloríficas ($\gamma > 1$). |
| **Proceso Adiabático (P-V)** | $P V^\gamma = \text{constante}$ | Relación presión-volumen para un gas ideal en un proceso adiabático cuasiestático. |
| **Proceso Adiabático (T-V)** | $T V^{\gamma - 1} = \text{constante}$ | Relación temperatura-volumen en un proceso adiabático cuasiestático. |
| **Proceso Adiabático (P-T)** | $P^{1-\gamma} T^\gamma = \text{constante}$ | Relación presión-temperatura en un proceso adiabático cuasiestático. |
| **Trabajo Adiabático (Gas Ideal)** | $W = \frac{P_1 V_1 - P_2 V_2}{\gamma - 1} = n C_v (T_1 - T_2)$ | Trabajo producido/requerido en un proceso sin transferencia de calor. |
| **Eficiencia Térmica General** | $\eta = 1 - \frac{\|Q_C\|}{\|Q_H\|}$ | Rendimiento de cualquier máquina térmica que opera en ciclo. |
| **Coeficiente de Rendimiento (Refrigerador)** | $K = \frac{\|Q_C\|}{W} = \frac{\|Q_C\|}{\|Q_H\| - \|Q_C\|}$ | Medida de eficacia de un refrigerador. |
| **Coeficiente de Rendimiento (Bomba de Calor)** | $COP_{HP} = \frac{\|Q_H\|}{W} = K + 1$ | Medida de eficacia de una bomba de calor para calefacción. |
| **Eficiencia de Carnot** | $\eta_{Carnot} = 1 - \frac{T_C}{T_H}$ | Eficiencia máxima teórica posible entre dos temperaturas $T_H$ y $T_C$. |
| **Rendimiento Refrigerador de Carnot** | $K_{Carnot} = \frac{T_C}{T_H - T_C}$ | Coeficiente de desempeño máximo reversible para refrigeración. |
| **Eficiencia del Ciclo Otto** | $\eta_{Otto} = 1 - \frac{1}{r^{\gamma - 1}}$ | Eficiencia ideal de un motor a gasolina según su relación de compresión $r$. |
| **Eficiencia del Ciclo Diesel** | $\eta_{Diesel} = 1 - \frac{1}{r^{\gamma - 1}} \left[ \frac{r_c^\gamma - 1}{\gamma (r_c - 1)} \right]$ | Eficiencia ideal de un motor a gasoil según la relación de compresión $r$ y de corte $r_c$. |
| **Coeficiente de Joule-Thomson** | $\mu_{JT} = \left(\frac{\partial T}{\partial P}\right)_H$ | Relación del cambio de temperatura respecto a la presión en estrangulamiento. |
