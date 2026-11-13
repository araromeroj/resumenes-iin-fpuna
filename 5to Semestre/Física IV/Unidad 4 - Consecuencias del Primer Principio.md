# Unidad IV: Consecuencias del Primer Principio de la Termodinámica

---

## 1. Introducción y Fundamentos Termodinámicos

El **Primer Principio de la Termodinámica** establece el principio de conservación de la energía para sistemas termodinámicos. Expresa que la variación de energía interna de un sistema ($\Delta U$) es igual al calor neto entregado al sistema ($Q$) menos el trabajo neto realizado por el sistema ($W$):

$$Q - W = \Delta U \quad \text{(Forma macroscópica)}$$
$$dQ - dW = dU \quad \text{(Forma diferencial)}$$

Para procesos cuasiestáticos donde la única interacción de trabajo es de tipo hidrostático (trabajo de expansión o compresión de un fluido), el trabajo diferencial se define como $dW = P \, dV$. Por ende:

$$dQ = dU + P \, dV$$

Dado que la **energía interna ($U$)** es una **función de estado**, su diferencial $dU$ es una diferencial exacta. Las variables de estado macroscópicas ($P, V, T$) se vinculan mediante una **ecuación de estado** $f(P, V, T) = 0$. En consecuencia, solo dos de estas tres variables son independientes para describir el estado de una sustancia pura de masa constante.

---

## 2. Ecuaciones Independientes y Coeficientes Termodinámicos

### 2.1. Temperatura ($T$) y Volumen ($V$) como Variables Independientes

Consideremos la energía interna molar o específica en función de $T$ y $V$: $u = u(T, V)$.
La diferencial total exacta de $u$ viene dada por:

$$du = \left( \frac{\partial u}{\partial T} \right)_V dT + \left( \frac{\partial u}{\partial V} \right)_T dV$$

Sustituyendo $du$ en la primera ley $dQ = du + P \, dv$:

$$dQ = \left( \frac{\partial u}{\partial T} \right)_V dT + \left[ \left( \frac{\partial u}{\partial V} \right)_T + P \right] dv$$

#### Capacidad Calorífica a Volumen Constante ($C_v$)
Para un proceso isocórico ($dv = 0$), no existe trabajo hidrostático. La capacidad calorífica molar a volumen constante se define como:

$$C_v = \left( \frac{dQ}{dT} \right)_V = \left( \frac{\partial u}{\partial T} \right)_V$$

Sustituyendo esta definición en la ecuación de $dQ$:

$$dQ = C_v \, dT + \left[ \left( \frac{\partial u}{\partial V} \right)_T + P \right] dv$$

---

### 2.2. Temperatura ($T$) y Presión ($P$) como Variables Independientes

Para estudiar procesos a presión constante, es conveniente introducir la función de estado denominada **Entalpía ($H$)**.

#### Definición de Entalpía
$$H = U + P V \quad \implies \quad h = u + P v$$

Diferenciando la entalpía específica:

$$dh = du + P \, dv + v \, dP$$

Sustituyendo $du + P \, dv = dQ$ (de la primera ley):

$$dh = dQ + v \, dP \implies dQ = dh - v \, dP$$

Si consideramos la entalpía en función de $T$ y $P$: $h = h(T, P)$, su diferencial exacta es:

$$dh = \left( \frac{\partial h}{\partial T} \right)_P dT + \left( \frac{\partial h}{\partial P} \right)_T dP$$

Sustituyendo en la expresión de $dQ$:

$$dQ = \left( \frac{\partial h}{\partial T} \right)_P dT + \left[ \left( \frac{\partial h}{\partial P} \right)_T - v \right] dP$$

#### Capacidad Calorífica a Presión Constante ($C_p$)
Para un proceso isobárico ($dP = 0$):

$$C_p = \left( \frac{dQ}{dT} \right)_P = \left( \frac{\partial h}{\partial T} \right)_P$$

Reemplazando en la ecuación diferencial de transferencia de calor:

$$dQ = C_p \, dT + \left[ \left( \frac{\partial h}{\partial P} \right)_T - v \right] dP$$

---

## 3. Experimentos Fundamentales y Propiedades de Gases Ideales

### 3.1. Experimento de Joule (Expansión Libre)
En la expansión libre de Joule, un gas originalmente contenido en un recipiente rígido de volumen $V_1$ se expande hacia un recipiente evacuado de volumen $V_2$, estando ambos dentro de un baño de agua térmicamente aislado.

1. **Aislamiento térmico:** $Q = 0$
2. **Sin paredes móviles (expansión contra el vacío):** $W = 0$
3. **Primera Ley:** $\Delta U = Q - W = 0 \implies U_1 = U_2$

Joule observó experimentalmente que la temperatura del baño no sufría variación apreciable ($\Delta T = 0$). Dado que $du = 0$ y $dT = 0$:

$$\left( \frac{\partial u}{\partial v} \right)_T = 0 \quad \text{(Propiedad fundamental del gas ideal)}$$

**Conclusión:** Para un gas ideal, la energía interna depende únicamente de la temperatura:

$$u = u(T) \implies du = C_v \, dT \quad \text{y} \quad \Delta U = n C_v \Delta T$$

### 3.2. Experimento de Joule-Thomson (Efecto Joule-Kelvin)
El experimento consiste en el flujo continuo de un fluido a través de un tapón poroso o válvula de estrangulamiento térmicamente aislada ($Q = 0$).

#### Naturaleza Isoentálpica del Proceso de Estrangulamiento
Considerando un volumen de control entre la entrada (estado 1) y la salida (estado 2):
* Trabajo realizado por el pistón de entrada: $W_1 = -P_1 V_1$
* Trabajo realizado por el pistón de salida: $W_2 = P_2 V_2$
* Trabajo neto: $W_{neto} = P_2 V_2 - P_1 V_1$

Por el primer principio:

$$U_2 - U_1 = Q - W_{neto} = 0 - (P_2 V_2 - P_1 V_1)$$
$$U_2 + P_2 V_2 = U_1 + P_1 V_1 \implies H_1 = H_2$$

El proceso de estrangulamiento ocurre a **entalpía constante ($H = \text{constante}$)**.

#### Coeficiente de Joule-Thomson ($\mu_{JT}$)
Se define como la pendiente de la curva isoentálpica en un plano $T-P$:

$$\mu_{JT} = \left( \frac{\partial T}{\partial P} \right)_H$$

* Si $\mu_{JT} > 0$: El gas se **enfría** al expandirse ($dP < 0 \implies dT < 0$).
* Si $\mu_{JT} < 0$: El gas se **calienta** al expandirse ($dP < 0 \implies dT > 0$).
* Si $\mu_{JT} = 0$: No hay cambio de temperatura. Para un **gas ideal**, $\mu_{JT} = 0$.

---

## 4. Relación entre Capacidades Caloríficas ( Relación de Mayer )

Para un gas ideal:
$$h = u + Pv = u(T) + RT$$

Derivando con respecto a $T$:

$$\left( \frac{\partial h}{\partial T} \right)_P = \left( \frac{\partial u}{\partial T} \right)_V + R$$

Sustituyendo las definiciones de $C_p$ y $C_v$:

$$C_p - C_v = R \quad \text{(Relación de Mayer molar)}$$

Definiendo la razón de capacidades caloríficas ($\gamma$):

$$\gamma = \frac{C_p}{C_v}$$

Podemos expresar las capacidades caloríficas molares en función de $\gamma$ y $R$:

$$C_v = \frac{R}{\gamma - 1}, \qquad C_p = \frac{\gamma R}{\gamma - 1}$$

* **Gas monoatómico** ($He, Ar$): $C_v = \frac{3}{2}R$, $C_p = \frac{5}{2}R$, $\gamma = \frac{5}{3} \approx 1{,}67$
* **Gas diatómico** ($N_2, O_2, \text{aire}$): $C_v = \frac{5}{2}R$, $C_p = \frac{7}{2}R$, $\gamma = \frac{7}{5} = 1{,}40$

---

## 5. Procesos Adiabáticos en Gases Ideales

Un proceso cuasiestático y adiabático ($dQ = 0$) en un gas ideal cumple:

$$dU = -dW \implies n C_v dT = -P dV$$

Usando la ecuación de estado $P V = n R T \implies P = \frac{n R T}{V}$:

$$n C_v dT = -\frac{n R T}{V} dV \implies \frac{dT}{T} = -\frac{R}{C_v} \frac{dV}{V}$$

Sabiendo que $\frac{R}{C_v} = \gamma - 1$:

$$\frac{dT}{T} + (\gamma - 1) \frac{dV}{V} = 0$$

Integrando entre dos estados:

$$\ln\left(\frac{T_2}{T_1}\right) + \ln\left(\frac{V_2}{V_1}\right)^{\gamma - 1} = 0 \implies T_1 V_1^{\gamma - 1} = T_2 V_2^{\gamma - 1} = \text{constante}$$

### Ecuaciones de Estado para un Proceso Adiabático Reversible:

1. **Relación $T-V$:**
   $$T V^{\gamma - 1} = \text{constante}$$

2. **Relación $P-V$:** (Sustituyendo $T = \frac{PV}{nR}$)
   $$P V^{\gamma} = \text{constante}$$

3. **Relación $T-P$:** (Sustituyendo $V = \frac{nRT}{P}$)
   $$T^{\gamma} P^{1 - \gamma} = \text{constante} \quad \implies \quad T P^{\frac{1 - \gamma}{\gamma}} = \text{constante}$$

### Trabajo en un Proceso Adiabático:
$$W = -\Delta U = -n C_v (T_2 - T_1) = \frac{P_1 V_1 - P_2 V_2}{\gamma - 1}$$

---

## 6. Máquinas Térmicas y Ciclos Termodinámicos

Una **máquinas térmica** es un dispositivo operacional continuo que opera en ciclo absorbiendo calor $Q_H$ de una fuente caliente ($T_H$), realizando un trabajo mecánico $W$, y rechazando calor $Q_C$ a una fuente fría ($T_C$).

### Rendimiento o Eficiencia Térmica ($\eta$ o $e$):
Por la conservación de la energía en un ciclo ($\Delta U_{ciclo} = 0$):

$$W = Q_H - |Q_C|$$

$$\eta = \frac{W}{Q_H} = \frac{Q_H - |Q_C|}{Q_H} = 1 - \frac{|Q_C|}{Q_H}$$

---

### 6.1. Ciclo de Carnot
El ciclo de Carnot es el ciclo reversible idealizado que establece el límite de eficiencia máxima teórica entre dos fuentes térmicas a $T_H$ y $T_C$.

#### Diagrama de Procesos del Ciclo de Carnot ($P-V$):
1. **$a \to b$:** Expansión isotérmica a $T_H$ (absorbe $Q_H = n R T_H \ln\frac{V_b}{V_a}$).
2. **$b \to c$:** Expansión adiabática de $T_H$ a $T_C$ ($T_H V_b^{\gamma-1} = T_C V_c^{\gamma-1}$).
3. **$c \to d$:** Compresión isotérmica a $T_C$ (cede $|Q_C| = n R T_C \ln\frac{V_c}{V_d}$).
4. **$d \to a$:** Compresión adiabática de $T_C$ a $T_H$ ($T_C V_d^{\gamma-1} = T_H V_a^{\gamma-1}$).

Relación entre volúmenes: $\frac{V_b}{V_a} = \frac{V_c}{V_d}$.

#### Eficiencia Térmica de Carnot:
$$\frac{|Q_C|}{Q_H} = \frac{T_C}{T_H} \implies \eta_{\text{Carnot}} = 1 - \frac{T_C}{T_H}$$

---

### 6.2. Ciclo Otto (Motor a Gasolina)
El ciclo Otto es el modelo ideal para motores de combustión interna de encendido por chispa.

#### Definición de Estados y Procesos:
* **$a \to b$:** Compresión adiabática (Carrera de compresión, volumen disminuye de $V_a = rV$ a $V_b = V$).
* **$b \to c$:** Calentamiento isocórico (Combustión instantánea por chispa, absorbe $Q_H$).
* **$c \to d$:** Expansión adiabática (Carrera de potencia o trabajo).
* **$d \to a$:** Enfriamiento isocórico (Rechazo de gases de escape, cede $|Q_C|$).

#### Parámetro Clave:
* **Razón de compresión ($r$):**
  $$r = \frac{V_{máx}}{V_{mín}} = \frac{V_a}{V_b}$$

#### Deducción de la Eficiencia del Ciclo Otto:
Calores transferidos a volumen constante:

$$Q_H = n C_v (T_c - T_b)$$
$$|Q_C| = n C_v (T_d - T_a)$$

Eficiencia:

$$\eta_{\text{Otto}} = 1 - \frac{|Q_C|}{Q_H} = 1 - \frac{T_d - T_a}{T_c - T_b}$$

Para los procesos adiabáticos $a \to b$ y $c \to d$:

$$T_b = T_a r^{\gamma - 1}, \qquad T_c = T_d r^{\gamma - 1}$$

Sustituyendo $T_b$ y $T_c$:

$$T_c - T_b = (T_d - T_a) r^{\gamma - 1}$$

Reemplazando en la ecuación de la eficiencia:

$$\eta_{\text{Otto}} = 1 - \frac{1}{r^{\gamma - 1}}$$

---

### 6.3. Ciclo Diesel (Motor a Inyección por Compresión)
El ciclo Diesel idealiza los motores de combustión interna por autoencendido. La combustión no ocurre a volumen constante, sino a **presión constante**.

#### Definición de Estados y Procesos:
* **$a \to b$:** Compresión adiabática de volumen $rV$ a $V$.
* **$b \to c$:** Calentamiento isobárico a presión $P_b = P_c$ (Inyección y combustión del diésel, absorbe $Q_H$).
* **$c \to d$:** Expansión adiabática (Carrera de trabajo).
* **$d \to a$:** Enfriamiento isocórico a volumen $rV$ (Escape de gases, cede $|Q_C|$).

#### Parámetros Clave:
* **Razón de compresión ($r$):** $r = \frac{V_a}{V_b}$
* **Razón de corte de combustión ($r_c$):** $r_c = \frac{V_c}{V_b}$

#### Deducción de la Eficiencia del Ciclo Diesel:
$$Q_H = n C_p (T_c - T_b)$$
$$|Q_C| = n C_v (T_d - T_a)$$

Eficiencia térmica:

$$\eta_{\text{Diesel}} = 1 - \frac{|Q_C|}{Q_H} = 1 - \frac{n C_v (T_d - T_a)}{n C_p (T_c - T_b)} = 1 - \frac{1}{\gamma} \left( \frac{T_d - T_a}{T_c - T_b} \right)$$

Expresando en términos de $r$ y $r_c$:

$$\eta_{\text{Diesel}} = 1 - \frac{1}{r^{\gamma - 1}} \left[ \frac{r_c^{\gamma} - 1}{\gamma (r_c - 1)} \right]$$

---

## 7. Resumen de Fórmulas de la Unidad

| Nombre de la Fórmula                     | Fórmula en LaTeX                                                                                               | Descripción y Aplicación                                                          |
| :--------------------------------------- | :------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------- |
| **Primera Ley (Diferencial)**            | $dQ = dU + P \, dV$                                                                                            | Balance energético infinitesimal para procesos cuasiestáticos.                    |
| **Definición de Entalpía**               | $H = U + P V$                                                                                                  | Función de estado ideal para procesos a presión constante.                        |
| **Capacidad Calorífica ($V$ constante)** | $C_v = \left( \frac{\partial u}{\partial T} \right)_V$                                                         | Tasa de cambio de la energía interna respecto a $T$ a volumen constante.          |
| **Capacidad Calorífica ($P$ constante)** | $C_p = \left( \frac{\partial h}{\partial T} \right)_P$                                                         | Tasa de cambio de la entalpía respecto a $T$ a presión constante.                 |
| **Ecuación de Joule (Gas Ideal)**        | $\left( \frac{\partial u}{\partial v} \right)_T = 0$                                                           | Indica que la energía interna de un gas ideal solo depende de $T$.                |
| **Coeficiente Joule-Thomson**            | $\mu_{JT} = \left( \frac{\partial T}{\partial P} \right)_H$                                                    | Mide el cambio de temperatura durante una expansión isoentálpica.                 |
| **Relación de Mayer**                    | $C_p - C_v = R$                                                                                                | Relación entre las capacidades caloríficas molares de un gas ideal.               |
| **Razón de Capacidades Caloríficas**     | $\gamma = \frac{C_p}{C_v}$                                                                                     | Coeficiente adiabático del gas.                                                   |
| **Proceso Adiabático ($T-V$)**           | $T V^{\gamma - 1} = \text{constante}$                                                                          | Relación entre temperatura y volumen en expansión/compresión adiabática.          |
| **Proceso Adiabático ($P-V$)**           | $P V^{\gamma} = \text{constante}$                                                                              | Ecuación de estado del camino para procesos adiabáticos reversibles.              |
| **Proceso Adiabático ($T-P$)**           | $T P^{\frac{1 - \gamma}{\gamma}} = \text{constante}$                                                           | Relación entre temperatura y presión en procesos adiabáticos.                     |
| **Entalpía en Procesos Adiabáticos**     | $H=n.C_p(T_2-T_1)$                                                                                             |                                                                                   |
| **Trabajo Adiabático**                   | $W = \frac{P_1 V_1 - P_2 V_2}{\gamma - 1}$                                                                     | Trabajo realizado por/sobre el gas en un proceso adiabático.                      |
| **Eficiencia Térmica General**           | $\eta = 1 - \frac{\|Q_C\|}{Q_H}$                                                                               | Eficiencia de cualquier máquina térmica que opera en ciclo.                       |
| **Eficiencia de Carnot**                 | $\eta_{\text{Carnot}} = 1 - \frac{T_C}{T_H}$                                                                   | Eficiencia máxima teórica asignada a dos fuentes térmicas a $T_H$ y $T_C$.        |
| **Eficiencia Ciclo Otto**                | $\eta_{\text{Otto}} = 1 - \frac{1}{r^{\gamma - 1}}$                                                            | Eficiencia ideal de un motor a gasolina en función de la razón de compresión $r$. |
| **Eficiencia Ciclo Diesel**              | $\eta_{\text{Diesel}} = 1 - \frac{1}{r^{\gamma - 1}} \left[ \frac{r_c^{\gamma} - 1}{\gamma (r_c - 1)} \right]$ | Eficiencia ideal de un motor diésel en función de $r$ y la razón de corte $r_c$.  |
