
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

---

Entender cuándo una fuente térmicamente interviene, cómo influye la transferencia de calor y cuándo varía o no la entropía es la clave central de la termodinámica.
### 1. ¿Qué es una Fuente Térmica (o Depósito Térmico)?

**Definición:** Una **fuente térmica** o reserva de calor es un sistema capaz de absorber o ceder una cantidad arbitraria de calor sin que su temperatura cambie apreciablemente.
- **Ejemplos cotidianos:** El océano, la atmósfera terrestre, la superficie del Sol o un gran baño de agua con hielo.
- **Característica fundamental:** Opera de forma isotérmica ($T = \text{constante}$).
### 2. Signos del Calor ($Q$): Ceder vs. Absorber Calor

El sentido de la transferencia de calor se rige por la convención internacional de signos de la termodinámica:
- **La fuente CEDE calor (pierde calor):**  
    - **¿Cuándo pasa?** Cuando la fuente está a una temperatura mayor que el cuerpo o sistema con el que entra en contacto térmico (el calor fluye espontáneamente del objeto más caliente al más frío).
    - **Signo matemático:** **$Q_{\text{fuente}} < 0$** (es negativo).    
    - **Consecuencia:** La fuente **pierde energía interna**.    
- **La fuente ABSORBE calor (gana calor):**  
    - **¿Cuándo pasa?** Cuando la fuente está a una temperatura menor que el cuerpo o sistema que le transfiere energía.    
    - **Signo matemático:** **$Q_{\text{fuente}} > 0$** (es positivo).     
    - **Consecuencia:** La fuente **gana energía interna**.
### 3. Entropía en una Fuente Térmica: ¿Cuándo TIENE variación y cuándo NO?

Por definición, el cambio de entropía diferencial de cualquier proceso reversible está dado por:

$$dS = \frac{dQ_{\text{rev}}}{T}$$

Puesto que una fuente térmica permanece a **temperatura constante ($T$)**, la variación total de su entropía al intercambiar calor es simplemente:

$$\Delta S_{\text{fuente}} = \frac{Q_{\text{fuente}}}{T_{\text{fuente}}}$$

#### **A. ¿Cuándo la fuente SÍ TIENE cambio de entropía ($\Delta S_{\text{fuente}} \neq 0$)?**

Siempre que la fuente **intercambie calor** con el exterior o con otro cuerpo:
1. **Si CEDE calor ($Q < 0$):**
    $$\Delta S_{\text{fuente}} = \frac{-Q}{T} < 0$$
    
    _La entropía de la fuente **disminuye**._
1. **Si ABSORBE calor ($Q > 0$):**
    $$\Delta S_{\text{fuente}} = \frac{+Q}{T} > 0$$
    
    _La entropía de la fuente **aumenta**._
    
#### **B. ¿Cuándo la fuente NO TIENE cambio de entropía ($\Delta S_{\text{fuente}} = 0$)?**

Una fuente (o un elemento dentro del sistema) **NO cambia su entropía** en los siguientes momentos específicos:
1. **Proceso Adiabático ($Q = 0$):** Si la fuente o el objeto está térmicamente aislado y no gana ni pierde calor.
2. **Sustancia en Régimen Estacionario / Máquina Térmica:**  
    - La sustancia de trabajo dentro de una máquina térmica o resistencia en estado estacionario (como en el _Ejercicio 1_ del ejercitario) no almacena calor ni cambia sus propiedades termodinámicas a lo largo del tiempo. Al no cambiar sus variables de estado, su variación de entropía nula ($\Delta S = 0$).    
3. **Disipación pura de trabajo eléctrico (Fuente que genera calor):**  
    - Cuando una resistencia convierte trabajo eléctrico directamente en calor sin cambiar sus propias propiedades de estado, la entropía de la resistencia no varía ($\Delta S_{\text{resistencia}} = 0$), y todo el cambio de entropía ocurre en el medio ambiente que recibe dicho calor.    

### 4. Cuadro Resumen Integrador

| Situación de la Fuente                                      | Flujo de Calor (QQQ)            | Variación de Entropía (ΔS=QT\Delta S = \frac{Q}{T}ΔS=TQ​) | ¿Qué le pasa a la entropía de la fuente? |
| ----------------------------------------------------------- | ------------------------------- | --------------------------------------------------------- | ---------------------------------------- |
| **Cede calor** (Foco caliente hacia un cuerpo más frío)     | $Q < 0$ (Negativo)              | $\Delta S < 0$                                            | **Disminuye**                            |
| **Absorbe calor** (Foco frío recibiendo calor)              | $Q > 0$ (Positivo)              | $\Delta S > 0$                                            | **Aumenta**                              |
| **Sin transferencia de calor** (Aislamiento o adiabático)   | $Q = 0$                         | $\Delta S = 0$                                            | **Permanece constante**                  |
| **Dispositivo en régimen permanente** (Resistencia/máquina) | $Q_{\text{neto}} = 0$ por ciclo | $\Delta S = 0$                                            | **No cambia**                            |

### 5. Regla de Oro para la Entropía del Universo ($\Delta S_{\text{universo}}$)
Es vital no confundir la **entropía de la fuente** con la **entropía del universo**:
- La entropía de una fuente individual **sí puede disminuir** cuando cede calor ($\Delta S_{\text{fuente}} < 0$).
- Sin embargo, la entropía total del universo ($\Delta S_{\text{universo}} = \Delta S_{\text{sistema}} + \Delta S_{\text{fuente}}$) **siempre aumenta** ($\Delta S_{\text{universo}} > 0$) en cualquier proceso real e irreversible, debido a que la fuente que recibe el calor a menor temperatura siempre gana más entropía que la entropía que pierde la fuente más caliente que cede el calor.