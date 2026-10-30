# Unidad VI: Entropía

## 1. Introducción y Desigualdad de Clausius

### Desigualdad de Clausius
El Teorema o Desigualdad de Clausius establece que para cualquier proceso cíclico se cumple la siguiente relación:

$$\oint \frac{dQ}{T} \le 0$$

* **Procesos Reversibles (Ideales):** Se cumple la igualdad ($\oint \frac{dQ}{T} = 0$), como en el ciclo de Carnot.
* **Procesos Irreversibles (Reales):** Se cumple la estricta desigualdad ($\oint \frac{dQ}{T} < 0$).

Esta relación expresa que, durante la realización de un proceso real, la entropía entregada al ambiente es mayor que la entropía recibida por las fuentes térmicas.

---

## 2. Definición de Entropía

La **entropía ($S$)** es una función de estado cuyo cambio determina la posibilidad o imposibilidad de que ocurra un proceso termodinámico.

Para un proceso cíclico reversible arbitrario, este puede aproximarse mediante un número infinito de pequeños ciclos de Carnot. Sumando las contribuciones de calor a sus respectivas temperaturas y llevando la suma al límite, se obtiene:

$$\oint \frac{dQ_{r}}{T} = 0$$

Dado que la integral de línea alrededor de un camino cerrado es cero, el integrando diferencial representa una diferencial exacta. Se define la variación infinitesimal de entropía como:

$$dS = \frac{dQ_{r}}{T}$$

Para cualquier cambio entre un estado inicial $a$ y un estado final $b$:

$$\Delta S = S_b - S_a = \int_{a}^{b} dS = \int_{a}^{b} \frac{dQ_{r}}{T}$$

Unidades en el Sistema Internacional (S.I.): $\text{J/K}$ (Joules por Kelvin).

### Entropía Específica
La entropía es una propiedad **extensiva**. Se define la entropía específica ($s$) como la entropía por unidad de masa o por número de moles:

* Por unidad de masa: 
  $$s = \frac{S}{m}$$
* Por unidad de cantidad de sustancia (moles): 
  $$s = \frac{S}{n}$$

---

## 3. Cálculo de Variaciones de Entropía en Procesos Reversibles

Para calcular la variación de entropía $\Delta S$ en un proceso reversible, se integra la expresión $\int \frac{dQ}{T}$ según el comportamiento térmico del sistema.

### 3.1 Proceso Adiabático Reversible
En un proceso adiabático no hay transferencia de calor ($dQ = 0$).

$$\Delta S = \int \frac{0}{T} = 0$$

*(Un proceso adiabático reversible es isentrópico, es decir, ocurre a entropía constante).*

### 3.2 Proceso Isotérmico Reversible
La temperatura $T$ permanece constante durante la transferencia de calor ($T = \text{cte}$).

$$\Delta S = \frac{1}{T} \int dQ = \frac{Q}{T}$$

### 3.3 Proceso Isocórico Reversible
A volumen constante, el calor transferido es $dQ = n c_V dT$. Asumiendo la capacidad calorífica molar a volumen constante ($c_V$) como constante:

$$\Delta S = \int_{T_0}^{T_f} \frac{n c_V dT}{T} = n c_V \ln\left(\frac{T_f}{T_0}\right)$$

### 3.4 Proceso Isobárico Reversible
A presión constante, el calor transferido es $dQ = n c_P dT$. Asumiendo la capacidad calorífica molar a presión constante ($c_P$) como constante:

$$\Delta S = \int_{T_0}^{T_f} \frac{n c_P dT}{T} = n c_P \ln\left(\frac{T_f}{T_0}\right)$$

---

## 4. Variaciones de Entropía en Procesos Irreversibles

Puesto que la entropía es una **función de estado**, su variación $\Delta S$ depende únicamente de los estados inicial y final, y no de la trayectoria seguida. 

Para calcular $\Delta S$ en un proceso irreversible entre dos estados determinados, se diseña un proceso reversible ficticio que conecte el mismo estado inicial con el estado final y se integra $\int \frac{dQ_r}{T}$ a lo largo de esa trayectoria reversible.

---

## 5. Principio de Aumento de la Entropía

En todos los procesos reales (irreversibles) que se producen en la naturaleza, la entropía del Universo aumenta:

$$\Delta S_{\text{Universo}} > 0$$

En procesos reversibles hipotéticos, la entropía del Universo permanece constante ($\Delta S_{\text{Universo}} = 0$). Por lo tanto, para cualquier proceso en un sistema aislado:

$$\Delta S_{\text{aislado}} \ge 0$$

**Aspecto fundamental:** A diferencia de la energía (que se conserva, primer principio), la entropía **no se destruye, pero sí puede ser creada** (segundo principio de la termodinámica). Un aumento de entropía representa mayor desorden a nivel microscópico.

---

## 6. Entropía y Transformaciones Politrópicas

Una **transformación politrópica** es aquella en la cual la capacidad calorífica $C$ permanece constante durante el proceso.

El calor intercambiado en un proceso diferencial viene dado por:

$$dQ = n c d T$$

A partir del primer principio de la termodinámica ($dQ = C_V dT + p dV$) y la ecuación de estado del gas ideal ($p V = R T$), se define el **exponente politrópico ($n$)**:

$$n = \frac{C_P - C}{C_V - C}$$

La ecuación general de una transformación politrópica para un gas ideal es:

$$p V^n = \text{cte}$$

### Casos particulares según el valor de $n$:

1. **Proceso Isobárico ($p = \text{cte}$):** $C = C_P \implies n = 0$
2. **Proceso Isotérmico ($T = \text{cte}$):** $C = \infty \implies n = 1$
3. **Proceso Adiabático ($Q = 0$):** $C = 0 \implies n = \gamma = \frac{c_P}{c_V}$
4. **Proceso Isocórico ($V = \text{cte}$):** $C = C_V \implies n = \infty$

---

## Tabla Resumen de Fórmulas de la Unidad VI

| Nombre | Fórmula Matemática | Descripción |
| :--- | :--- | :--- |
| **Desigualdad de Clausius** | $\oint \frac{dQ}{T} \le 0$ | Criterio para procesos cíclicos ($\le 0$). La igualdad aplica a ciclos reversibles y la desigualdad a irreversibles. |
| **Definición de Entropía** | $dS = \frac{dQ_r}{T}$ | Variación infinitesimal de entropía definida en función del calor intercambiado de forma reversible y la temperatura absoluta. |
| **Variación de Entropía Total** | $\Delta S = S_b - S_a = \int_{a}^{b} \frac{dQ_r}{T}$ | Diferencia de entropía entre dos estados de equilibrio $a$ y $b$. |
| **Entropía Específica (Masa)** | $s = \frac{S}{m}$ | Entropía por unidad de masa del sistema ($J / (kg \cdot K)$). |
| **Entropía Específica (Moles)** | $s = \frac{S}{n}$ | Entropía por unidad de cantidad de sustancia ($J / (mol \cdot K)$). |
| **Entropía Proceso Adiabático Reversible** | $\Delta S = 0$ | Al no haber flujo de calor ($dQ=0$), la entropía permanece constante (proceso isentrópico). |
| **Entropía Proceso Isotérmico Reversible** | $\Delta S = \frac{Q}{T}$ | Cambio de entropía cuando la temperatura permanece constante durante la transferencia de calor. |
| **Entropía Proceso Isocórico Reversible** | $\Delta S = n c_V \ln\left(\frac{T_f}{T_0}\right)$ | Variación de entropía a volumen constante con capacidad calorífica $c_V$ constante. |
| **Entropía Proceso Isobárico Reversible** | $\Delta S = n c_P \ln\left(\frac{T_f}{T_0}\right)$ | Variación de entropía a presión constante con capacidad calorífica $c_P$ constante. |
| **Principio de Aumento de Entropía** | $\Delta S_{\text{Universo}} \ge 0$ | La entropía total de un sistema aislado o del Universo siempre aumenta en procesos reales e irreversibles. |
| **Exponente Politrópico** | $n = \frac{C_P - C}{C_V - C}$ | Relación de capacidades caloríficas que define el exponente de una transformación politrópica. |
| **Ecuación de Proceso Politrópico** | $p V^n = \text{cte}$ | Relación entre la presión y el volumen en transformaciones donde la capacidad calorífica se mantiene constante. |