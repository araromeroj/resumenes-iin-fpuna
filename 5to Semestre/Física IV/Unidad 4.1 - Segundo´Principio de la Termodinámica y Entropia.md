# Unidad V: Segundo Principio de la Termodinámica y Entropía

## 1. Introducción y Dirección de los Procesos Naturales

El **Primer Principio de la Termodinámica** establece la conservación de la energía, pero no impone ninguna restricción sobre la dirección en la que un proceso físico o químico puede ocurrir de manera natural. Sin embargo, la experiencia demuestra que los procesos en la naturaleza ocurren de forma **irreversible** y en un sentido único:

* El calor siempre fluye de manera espontánea desde un cuerpo a mayor temperatura hacia uno de menor temperatura, nunca a la inversa.
* Un gas se expande espontáneamente ocupando todo el volumen disponible del recipiente que lo contiene, pero jamás se comprime por sí solo hacia una fracción del volumen.
* El trabajo mecánico (como el rozamiento) puede transformarse íntegramente en calor, pero el calor no puede convertirse por completo en trabajo mecánico en un proceso cíclico.

El **Segundo Principio de la Termodinámica** introduce el criterio cuantitativo para determinar la direccionalidad de los procesos térmicos, la reversibilidad o irreversibilidad de las transformaciones, la imposibilidad de construir ciertas máquinas térmicas ideales y la definición de una nueva función de estado clave: la **Entropía ($S$)**.

---

## 2. Definición Absoluta de Temperatura y Escala Kelvin

### 2.1. Escala Termodinámica de Temperatura

A diferencia de las escalas termométricas empíricas ($\theta$), que dependen de las propiedades térmicas de sustancias específicas (dilatación de mercurio, resistencia de un platino, etc.), Lord Kelvin propuso una escala de temperatura independiente del fluido de trabajo utilizada en un ciclo de Carnot.

Para un ciclo de Carnot que opera entre dos fuentes térmicas a temperaturas empíricas $\theta_H$ (foco caliente) y $\theta_C$ (foco frío):

$$
\frac{|Q_C|}{Q_H} = f(\theta_C, \theta_H)
$$

Mediante un análisis de ciclos en serie (tres fuentes térmicas a $\theta_1, \theta_2, \theta_3$), se deduce matemáticamente que la función $f(\theta_C, \theta_H)$ se puede descomponer en el cociente de una función que depende de cada temperatura por separado:

$$
\frac{|Q_C|}{Q_H} = \frac{\phi(\theta_C)}{\phi(\theta_H)}
$$

Kelvin definió la **temperatura absoluta o termodinámica ($T$)** como proporcional a la función $\phi(\theta)$:

$$
\frac{|Q_C|}{Q_H} = \frac{T_C}{T_H} \quad \implies \quad \frac{Q_H}{T_H} - \frac{|Q_C|}{T_C} = 0
$$

### 2.2. El Cero Absoluto de Temperatura

Dado que las cantidades de calor intercambiadas $|Q_C|$ y $Q_H$ son magnitudes físicamente positivas para un ciclo de Carnot que opera como máquina térmica:

$$
T_C = T_H \left( \frac{|Q_C|}{Q_H} \right)
$$

* Si $|Q_C| \to 0$, entonces $T_C \to 0\text{ K}$.
* El **Cero Absoluto ($0\text{ K}$)** representa la temperatura teórica a la cual la entropía y el movimiento cinético atómico/molecular alcanzan un valor mínimo fundamental.
* Puesto que $|Q_C|$ no puede ser negativo, **la temperatura termodinámica en la escala Kelvin es siempre estrictamente no negativa ($T \ge 0\text{ K}$)**.

---

## 3. Enunciados Clásicos del Segundo Principio

Existen varios enunciados equivalentes para el Segundo Principio de la Termodinámica. Aunque abordan la ley desde distintos enfoques (máquinas térmicas vs. refrigeradores), son matemáticamente equivalentes: la violación de uno implica de forma directa la violación del otro.

### 3.1. Enunciado de Kelvin-Planck (Máquinas Térmicas)

> *"Es imposible construir una máquina térmica que, operando en un ciclo, no produzca otro efecto que extraer calor de un único depósito térmico y realizar una cantidad equivalente de trabajo neto."*

$$
W_{\text{neto}} \ne Q_H \quad \implies \quad \eta = \frac{W}{Q_H} < 1 \quad (100\%)
$$

**Implicación:** Toda máquina térmica cíclica debe ceder obligatoriamente una parte del calor recibido a un foco frío ($|Q_C| > 0$).

### 3.2. Enunciado de Clausius (Refrigeradores y Bombas de Calor)

> *"Es imposible construir un dispositivo que opere en un ciclo y cuyo único resultado sea la transferencia de calor de un cuerpo de menor temperatura a otro de mayor temperatura."*

**Implicación:** Para lograr que el calor fluya desde un cuerpo frío hacia un cuerpo caliente, es imprescindible aportar un trabajo mecánico exterior ($W_{\text{entrada}} > 0$).

---

## 4. Teorema y Desigualdad de Clausius

### 4.1. Teorema de Clausius

Para un ciclo reversible cualquiera que intercambia calor con múltiples fuentes térmicas a distintas temperaturas $T_i$, el balance integral dividiendo entre las respectivas temperaturas absolutas satisface:

$$
\sum_{i} \frac{Q_i}{T_i} = 0 \quad \xrightarrow{\text{límite continuo}} \quad \oint \frac{dQ_{\text{rev}}}{T} = 0
$$

### 4.2. Desigualdad de Clausius

Si el ciclo presenta irreversibilidad alguna en su interior o en el intercambio térmico con el entorno:

$$
\oint \frac{dQ}{T} \le 0
$$

* **$\oint \frac{dQ}{T} = 0$**: Proceso cíclico **Reversible** (Ideal).
* **$\oint \frac{dQ}{T} < 0$**: Proceso cíclico **Irreversible** (Real).
* **$\oint \frac{dQ}{T} > 0$**: Proceso **Imposible** según la Segunda Ley.

---

## 5. La Entropía ($S$) como Función de Estado

### 5.1. Definición Matemática de Entropía

Dado que para cualquier ciclo reversible $\oint \frac{dQ_{\text{rev}}}{T} = 0$, la integral de línea de la cantidad $\frac{dQ_{\text{rev}}}{T}$ entre dos estados $A$ y $B$ es independiente de la trayectoria elegida. Por lo tanto, existe una función de estado matemática llamada **Entropía ($S$)**:

$$
dS = \left( \frac{dQ}{T} \right)_{\text{rev}}
$$

La variación de entropía $\Delta S$ entre un estado inicial $A$ y un estado final $B$ se calcula integrando a través de cualquier **camino cuasiestático y reversible**:

$$
\Delta S = S_B - S_A = \int_{A}^{B} \left( \frac{dQ}{T} \right)_{\text{rev}}
$$

Unidad en el Sistema Internacional (SI): **$[\text{J/K}]$** (Joules por Kelvin).

---

## 6. Principio del Aumento de Entropía

Para cualquier proceso real que lleve a un sistema desde un estado $A$ hasta un estado $B$:

$$
\int_{A}^{B} \frac{dQ}{T} \le S_B - S_A = \Delta S_{\text{sistema}}
$$

Considerando un **sistema aislado** (un sistema que no intercambia materia ni energía con el exterior, $dQ = 0$):

$$
\Delta S_{\text{sistema aislado}} \ge 0
$$

Dado que el **Universo** en su totalidad es el sistema aislado definitivo (compuesto por el *Sistema* bajo estudio más su *Entorno* o ambiente):

$$
\Delta S_{\text{universo}} = \Delta S_{\text{sistema}} + \Delta S_{\text{entorno}} \ge 0
$$

### Conclusiones Fundamentales:

1. **En procesos reversibles:** $\Delta S_{\text{universo}} = 0$
2. **En procesos irreversibles (reales):** $\Delta S_{\text{universo}} > 0$
3. **Imposibilidad:** No existe ningún proceso en el universo donde la entropía total disminuya ($\Delta S_{\text{universo}} < 0$).
4. **Conservación:** La energía se conserva ($U$), pero la entropía ($S$) **se crea** continuamente en los procesos irreversibles y jamás puede ser destruida.
5. **Criterio de Equilibrio:** El estado de equilibrio termodinámico de un sistema aislado corresponde a la condición de **entropía máxima**.

---

## 7. Cálculo de Variaciones de Entropía en Procesos Característicos

### 7.1. Fuente Térmica o Depósito a Temperatura Constante ($T_0$)
Una fuente cede o absorbe una cantidad de calor $Q$ manteniendo su temperatura fija:

$$
\Delta S_{\text{fuente}} = \frac{Q_{\text{fuente}}}{T_0}
$$

* Si la fuente **cede** calor: $Q < 0 \implies \Delta S_{\text{fuente}} < 0$.
* Si la fuente **absorbe** calor: $Q > 0 \implies \Delta S_{\text{fuente}} > 0$.

### 7.2. Cambio de Fase Isotérmico e Isobárico
Durante la fusión, vaporización o sublimación a presión constante ($T = \text{constante}$):

$$
\Delta S = \frac{m L}{T_{\text{cambio de fase}}}
$$

* $L > 0$ en fusión/vaporización/sublimación (absorbe calor).
* $L < 0$ en solidificación/condensación/deposición (cede calor).

### 7.3. Calentamiento o Enfriamiento de una Sustancia Incompresible (Líquido o Sólido)
Para una masa $m$ con calor específico constante $c_P$ que cambia de temperatura desde $T_i$ hasta $T_f$:

$$
dQ = m c_P dT \implies \Delta S = \int_{T_i}^{T_f} \frac{m c_P dT}{T} = m c_P \ln\left( \frac{T_f}{T_i} \right)
$$

### 7.4. Procesos en Gases Ideales

Partiendo del primer principio $dQ = n C_v dT + P dV$ o $dQ = n C_p dT - V dP$:

1. **En función de $(T, V)$:**
   

   $$
   \Delta S = n C_v \ln\left(\frac{T_f}{T_i}\right) + n R \ln\left(\frac{V_f}{V_i}\right)
   $$

2. **En función de $(T, P)$:**
   

   $$
   \Delta S = n C_p \ln\left(\frac{T_f}{T_i}\right) - n R \ln\left(\frac{P_f}{P_i}\right)
   $$

3. **En función de $(P, V)$:**
   

   $$
   \Delta S = n C_v \ln\left(\frac{P_f}{P_i}\right) + n C_p \ln\left(\frac{V_f}{V_i}\right)
   $$

---

## 8. Interpretación Estadística de la Entropía (Ecuación de Boltzmann)

Desde el punto de vista microfísico (desarrollado por Ludwig Boltzmann), la entropía es una medida del **desorden microscópico** o de la **probabilidad estadística** de una configuración macroscópica.

$$
S = k_B \ln(\Omega)
$$

Donde:
* **$k_B$**: Constante de Boltzmann ($k_B = 1{,}3806 \times 10^{-23} \text{ J/K} = \frac{R}{N_A}$).
* **$\Omega$**: Número de microestados accesibles compatibles con el macroestado termodinámico.

**Principio:** Los sistemas aislados evolucionan espontáneamente hacia el macroestado que posee el mayor número de microestados posibles ($\Omega_{\text{máx}}$), lo cual corresponde a la entropía máxima.

---

## 9. Tabla Resumen de Fórmulas de la Unidad V

| Nombre de la Fórmula | Fórmula en LaTeX | Descripción y Aplicación |
| :--- | :--- | :--- |
| **Escala Kelvin de Temperatura** | $\frac{\|Q_C\|}{Q_H} = \frac{T_C}{T_H}$ | Definición absoluta de temperatura mediante el ciclo de Carnot. |
| **Eficiencia Máxima (Carnot)** | $\eta_{\text{Carnot}} = 1 - \frac{T_C}{T_H}$ | Límite superior teórico de eficiencia entre dos temperaturas $T_H$ y $T_C$. |
| **Coeficiente de Eficiencia Refrigerador (Carnot)** | $K_{\text{Carnot}} = \frac{T_C}{T_H - T_C}$ | Eficiencia máxima posible para un refrigerador o congelador. |
| **Desigualdad de Clausius** | $\oint \frac{dQ}{T} \le 0$ | Criterio de reversibilidad ($=0$) e irreversibilidad ($<0$) en ciclos. |
| **Definición de Entropía** | $dS = \left( \frac{dQ}{T} \right)_{\text{rev}}$ | Diferencial de la función de estado Entropía en un camino reversible. |
| **Principio de Aumento de Entropía** | $\Delta S_{\text{universo}} = \Delta S_{\text{sist}} + \Delta S_{\text{entorno}} \ge 0$ | Establece que la entropía total del universo jamás disminuye. |
| **Entropía Foco Térmico** | $\Delta S_{\text{fuente}} = \frac{Q_{\text{fuente}}}{T_0}$ | Variación de entropía en una reserva a temperatura constante $T_0$. |
| **Entropía Cambio de Fase** | $\Delta S = \frac{m L}{T_{\text{fase}}}$ | Variación de entropía durante una transición de fase a $T$ fija. |
| **Entropía Calentamiento Sustancia** | $\Delta S = m c_P \ln\left(\frac{T_f}{T_i}\right)$ | Cambio de entropía en líquidos/sólidos con calor específico $c_P$. |
| **Entropía Gas Ideal $(T, V)$** | $\Delta S = n C_v \ln\left(\frac{T_f}{T_i}\right) + n R \ln\left(\frac{V_f}{V_i}\right)$ | Cambio de entropía en gas ideal en función de temperatura y volumen. |
| **Entropía Gas Ideal $(T, P)$** | $\Delta S = n C_p \ln\left(\frac{T_f}{T_i}\right) - n R \ln\left(\frac{P_f}{P_i}\right)$ | Cambio de entropía en gas ideal en función de temperatura y presión. |
| **Ecuación de Boltzmann** | $S = k_B \ln(\Omega)$ | Interpretación estadística de la entropía en función del número de microestados $\Omega$. |
