# Física III - Movimiento Oscilatorio (Oscilaciones Amortiguadas)

Resolución paso a paso de los ejercicios correspondientes a la unidad de Oscilaciones Amortiguadas.

## Ejercicio 1

**Enunciado:**
Un objeto de masa $10,6\text{ kg}$ oscila en el extremo de un resorte vertical con $k = 2,05 \times 10^2\text{ N/m}$, $b = 80,00\text{ N}\cdot\text{s/m}$. Determine:
(a) La frecuencia de la oscilación amortiguada.
(b) El porcentaje en que disminuye la amplitud en cada ciclo.
(c) El tiempo necesario para que la energía se reduzca a $50\%$ de su valor inicial.

**Datos:**

* $m = 10,6\text{ kg}$
* $k = 205\text{ N/m}$
* $b = 80,00\text{ N}\cdot\text{s/m}$

**Resolución paso a paso:**

### (a) Frecuencia de la oscilación amortiguada ($f_d$)

1. **Parámetro de amortiguamiento ($\gamma$) y frecuencia natural al cuadrado ($\omega_0^2$):**
   $$
   \gamma = \frac{b}{2m} = \frac{80,00\text{ N}\cdot\text{s/m}}{2(10,6\text{ kg})} \approx 3,7736\text{ s}^{-1}
   $$
   $$
   \omega_0^2 = \frac{k}{m} = \frac{205\text{ N/m}}{10,6\text{ kg}} \approx 19,3396\text{ rad}^2/\text{s}^2
   $$

2. **Frecuencia angular amortiguada ($\omega_d$):**
   $$
   \omega_d = \sqrt{\omega_0^2 - \gamma^2} = \sqrt{19,3396 - (3,7736)^2} = \sqrt{19,3396 - 14,2400} = \sqrt{5,0996} \approx 2,2582\text{ rad/s}
   $$

3. **Frecuencia lineal amortiguada ($f_d$):**
   $$
   f_d = \frac{\omega_d}{2\pi} = \frac{2,2582\text{ rad/s}}{2\pi} \approx 0,359\text{ Hz}
   $$

### (b) Porcentaje en que disminuye la amplitud en cada ciclo

1. **Período de la oscilación amortiguada ($T_d$):**
   $$
   T_d = \frac{1}{f_d} = \frac{1}{0,3594\text{ Hz}} \approx 2,782\text{ s}
   $$

2. **Relación entre amplitudes separadas un período $T_d$:**
   La envolvente de amplitud es $A(t) = A_0 e^{-\gamma t}$. Después de un ciclo ($t = T_d$):
   $$
   \frac{A(T_d)}{A_0} = e^{-\gamma T_d} = e^{-(3,7736\text{ s}^{-1})(2,782\text{ s})} = e^{-10,50} \approx 2,75 \times 10^{-5}
   $$

3. **Porcentaje de disminución:**
   $$
   \text{Disminución porcentual} = \left(1 - \frac{A(T_d)}{A_0}\right) \times 100\% = (1 - 0,0000275) \times 100\% \approx 99,997\%
   $$

### (c) Tiempo necesario para que la energía se reduzca al $50\%$ de su valor inicial

La energía mecánica decae exponencialmente según $E(t) = E_0 e^{-2\gamma t}$ (o $E(t) = E_0 e^{-t/\tau}$ con $\tau = \frac{m}{b}$).

Sustituimos $E(t) = 0,50 E_0$:
$$
0,50 E_0 = E_0 e^{-2\gamma t} \implies 0,50 = e^{-2\gamma t}
$$

Aplicamos logaritmo natural en ambos miembros:
$$
\ln(0,50) = -2\gamma t \implies -\ln(2) = -\frac{b}{m} t
$$

Despejamos $t$:
$$
t = \frac{m \ln(2)}{b} = \frac{(10,6\text{ kg})(0,69315)}{80,00\text{ N}\cdot\text{s/m}} \approx 0,0918\text{ s}
$$

## Ejercicio 2

**Enunciado:**
El sistema de suspensión de un automóvil está críticamente amortiguado. El período natural correspondiente al sistema sin amortiguamiento es $T_0 = 1\text{ s}$. Inicialmente, el sistema está desplazado una distancia $x_0$ respecto de la posición de equilibrio y se suelta desde el reposo. Determine:

* El desplazamiento del sistema después de $t = 1\text{ s}$, expresado en función de $x_0$.

**Datos:**

* Amortiguamiento crítico: $\gamma = \omega_0$
* Período natural: $T_0 = 1\text{ s}$
* Condiciones iniciales en $t = 0$: $x(0) = x_0$ y $v(0) = \dot{x}(0) = 0$

**Resolución paso a paso:**

1. **Cálculo de $\gamma$:**
   $$
   \omega_0 = \frac{2\pi}{T_0} = \frac{2\pi}{1\text{ s}} = 2\pi\text{ rad/s}
   $$
   Por condición de amortiguamiento crítico:
   $$
   \gamma = \omega_0 = 2\pi\text{ s}^{-1}
   $$

2. **Ecuación de movimiento para el caso críticamente amortiguado:**
   $$
   x(t) = e^{-\gamma t}(A + Bt)
   $$
   Derivamos respecto al tiempo para obtener la velocidad:
   $$
   \dot{x}(t) = -\gamma e^{-\gamma t}(A + Bt) + B e^{-\gamma t} = e^{-\gamma t}[B - \gamma(A + Bt)]
   $$

3. **Determinación de las constantes $A$ y $B$:**
   * En $t = 0$, $x(0) = x_0$:
     $$
     x(0) = e^{0}(A + B(0)) = A \implies A = x_0
     $$
   * En $t = 0$, $\dot{x}(0) = 0$:
     $$
     \dot{x}(0) = e^{0}[B - \gamma A] = 0 \implies B = \gamma A = \gamma x_0
     $$

   Sustituimos $A$ y $B$ en la ecuación de posición:
   $$
   x(t) = x_0 e^{-\gamma t}(1 + \gamma t)
   $$

4. **Evaluación en $t = 1\text{ s}$:**
   Sabiendo que $\gamma t = (2\pi\text{ s}^{-1})(1\text{ s}) = 2\pi$:
   $$
   x(1) = x_0 e^{-2\pi}(1 + 2\pi)
   $$
   Calculamos el valor numérico:
   $$
   x(1) = x_0 (0,0018674)(1 + 6,28319) = x_0 (0,0018674)(7,28319) \approx 0,0136\, x_0
   $$

## Ejercicio 3

**Enunciado:**
La frecuencia de un oscilador amortiguado es igual a la mitad de la frecuencia natural del mismo sistema sin amortiguamiento:
$$
\omega_d = \frac{\omega_0}{2}
$$
Determine:

* La razón entre las amplitudes de dos máximos sucesivos de la oscilación.

**Resolución paso a paso:**

1. **Relación entre $\gamma$ y $\omega_d$:**
   Partimos de la definición de frecuencia angular amortiguada:
   $$
   \omega_d = \sqrt{\omega_0^2 - \gamma^2} \implies \omega_d^2 = \omega_0^2 - \gamma^2
   $$
   Como $\omega_d = \frac{\omega_0}{2}$, entonces $\omega_0 = 2\omega_d$. Sustituimos:
   $$
   \omega_d^2 = (2\omega_d)^2 - \gamma^2 = 4\omega_d^2 - \gamma^2
   $$
   Despejamos $\gamma$:
   $$
   \gamma^2 = 3\omega_d^2 \implies \gamma = \sqrt{3}\,\omega_d
   $$

2. **Razón entre amplitudes de dos máximos sucesivos:**
   Dos máximos sucesivos están separados por un período amortiguado $T_d = \frac{2\pi}{\omega_d}$.
   La razón entre una amplitud máxima $A_n$ y la siguiente $A_{n+1}$ es:
   $$
   \frac{A_{n+1}}{A_n} = \frac{A_0 e^{-\gamma (t + T_d)}}{A_0 e^{-\gamma t}} = e^{-\gamma T_d}
   $$
   Sustituimos $\gamma = \sqrt{3}\,\omega_d$ y $T_d = \frac{2\pi}{\omega_d}$:
   $$
   \frac{A_{n+1}}{A_n} = e^{-(\sqrt{3}\,\omega_d)\left(\frac{2\pi}{\omega_d}\right)} = e^{-2\pi\sqrt{3}} \approx e^{-10,8828} \approx 1,88 \times 10^{-5}
   $$
   *(Nota: Si se expresa como la razón del máximo anterior respecto al siguiente, $\frac{A_n}{A_{n+1}} = e^{2\pi\sqrt{3}} \approx 5,32 \times 10^4$).*

## Ejercicio 4

**Enunciado:**
La velocidad terminal de una pelota de béisbol en caída libre es $v_T = 30\text{ m/s}$. Suponga que la fuerza de resistencia del aire es proporcional a la velocidad. La pelota se utiliza como masa de un péndulo de longitud $l = 1\text{ m}$. Determine:

* El período de las pequeñas oscilaciones del péndulo teniendo en cuenta el amortiguamiento producido por el aire.

**Datos:**

* $v_T = 30\text{ m/s}$
* $l = 1\text{ m}$
* $g = 9,8\text{ m/s}^2$

**Resolución paso a paso:**

1. **Relación entre la velocidad terminal y el parámetro $\gamma$:**
   En caída libre, una partícula alcanza su velocidad terminal $v_T$ cuando la fuerza de arrastre ($F_{\text{aire}} = b v_T$) equilibra exactamente a su peso ($mg$):
   $$
   b v_T = m g \implies \frac{b}{m} = \frac{g}{v_T}
   $$
   Como $\gamma = \frac{b}{2m}$, sustituimos:
   $$
   \gamma = \frac{g}{2 v_T} = \frac{9,8\text{ m/s}^2}{2(30\text{ m/s})} = \frac{9,8}{60} \approx 0,1633\text{ s}^{-1}
   $$

2. **Frecuencia angular natural del péndulo simple ($\omega_0$):**
   $$
   \omega_0^2 = \frac{g}{l} = \frac{9,8\text{ m/s}^2}{1\text{ m}} = 9,8\text{ rad}^2/\text{s}^2
   $$

3. **Frecuencia angular amortiguada ($\omega_d$):**
   $$
   \omega_d = \sqrt{\omega_0^2 - \gamma^2} = \sqrt{9,8 - (0,1633)^2} = \sqrt{9,8 - 0,02668} = \sqrt{9,7733} \approx 3,1262\text{ rad/s}
   $$

4. **Período de las oscilaciones amortiguadas ($T_d$):**
   $$
   T_d = \frac{2\pi}{\omega_d} = \frac{2\pi}{3,1262\text{ rad/s}} \approx 2,010\text{ s}
   $$

## Ejercicio 5

**Enunciado:**
Un sistema masa-resorte tiene $m = 2,0\text{ kg}$, $k = 72\text{ N/m}$. Considere sucesivamente los siguientes valores del coeficiente de amortiguamiento: $b_1 = 12\text{ N}\cdot\text{s/m}$, $b_2 = 24\text{ N}\cdot\text{s/m}$, $b_3 = 30\text{ N}\cdot\text{s/m}$. Determine:
(a) La frecuencia angular natural $\omega_0$.
(b) El coeficiente de amortiguamiento crítico $b_c$.
(c) El tipo de movimiento para cada valor de $b$.
(d) Para el caso subamortiguado, calcule $\omega_d$.

**Datos:**

* $m = 2,0\text{ kg}$
* $k = 72\text{ N/m}$

**Resolución paso a paso:**

### (a) Frecuencia angular natural ($\omega_0$)

$$
\omega_0 = \sqrt{\frac{k}{m}} = \sqrt{\frac{72\text{ N/m}}{2,0\text{ kg}}} = \sqrt{36} = 6,0\text{ rad/s}
$$

### (b) Coeficiente de amortiguamiento crítico ($b_c$)

En el amortiguamiento crítico se cumple $\gamma = \omega_0$, es decir, $\frac{b_c}{2m} = \omega_0$:
$$
b_c = 2m\omega_0 = 2(2,0\text{ kg})(6,0\text{ rad/s}) = 24\text{ N}\cdot\text{s/m}
$$

### (c) Tipo de movimiento para cada valor de $b$

Comparamos cada valor de $b$ con $b_c = 24\text{ N}\cdot\text{s/m}$ (o equivalentemente $\gamma = \frac{b}{2m}$ con $\omega_0 = 6,0\text{ rad/s}$):

* **Para $b_1 = 12\text{ N}\cdot\text{s/m}$:** Como $b_1 < b_c$ ($\gamma_1 = 3,0\text{ s}^{-1} < \omega_0$), el movimiento es **subamortiguado**.
* **Para $b_2 = 24\text{ N}\cdot\text{s/m}$:** Como $b_2 = b_c$ ($\gamma_2 = 6,0\text{ s}^{-1} = \omega_0$), el movimiento es **críticamente amortiguado**.
* **Para $b_3 = 30\text{ N}\cdot\text{s/m}$:** Como $b_3 > b_c$ ($\gamma_3 = 7,5\text{ s}^{-1} > \omega_0$), el movimiento es **sobreamortiguado**.

### (d) Frecuencia angular amortiguada ($\omega_d$) para el caso subamortiguado ($b_1 = 12\text{ N}\cdot\text{s/m}$)

Con $\gamma_1 = \frac{12}{2(2,0)} = 3,0\text{ s}^{-1}$:
$$
\omega_d = \sqrt{\omega_0^2 - \gamma_1^2} = \sqrt{(6,0)^2 - (3,0)^2} = \sqrt{36 - 9} = \sqrt{27} = 3\sqrt{3}\text{ rad/s} \approx 5,20\text{ rad/s}
$$

## Ejercicio 6

**Enunciado:**
Una masa de $0,50\text{ kg}$ está unida a un resorte de constante $k = 200\text{ N/m}$. El coeficiente de amortiguamiento es $b = 0,50\text{ N}\cdot\text{s/m}$, y la amplitud inicial es $A_0 = 8,0\text{ cm}$. Determine:
(a) $\gamma$, $\omega_0$ y $\omega_d$.
(b) El período de la oscilación amortiguada.
(c) El tiempo necesario para que la amplitud se reduzca a la mitad.
(d) La amplitud después de $10$ oscilaciones.

**Datos:**

* $m = 0,50\text{ kg}$
* $k = 200\text{ N/m}$
* $b = 0,50\text{ N}\cdot\text{s/m}$
* $A_0 = 8,0\text{ cm} = 0,080\text{ m}$

**Resolución paso a paso:**

### (a) $\gamma$, $\omega_0$ y $\omega_d$

* **Coeficiente $\gamma$:**
  $$
  \gamma = \frac{b}{2m} = \frac{0,50\text{ N}\cdot\text{s/m}}{2(0,50\text{ kg})} = 0,50\text{ s}^{-1}
  $$
* **Frecuencia angular natural $\omega_0$:**
  $$
  \omega_0 = \sqrt{\frac{k}{m}} = \sqrt{\frac{200\text{ N/m}}{0,50\text{ kg}}} = \sqrt{400} = 20\text{ rad/s}
  $$
* **Frecuencia angular amortiguada $\omega_d$:**
  $$
  \omega_d = \sqrt{\omega_0^2 - \gamma^2} = \sqrt{20^2 - (0,50)^2} = \sqrt{400 - 0,25} = \sqrt{399,75} \approx 19,994\text{ rad/s}
  $$

### (b) Período de la oscilación amortiguada ($T_d$)

$$
T_d = \frac{2\pi}{\omega_d} = \frac{2\pi}{19,994\text{ rad/s}} \approx 0,3143\text{ s}
$$

### (c) Tiempo para que la amplitud se reduzca a la mitad

Partimos de $A(t) = A_0 e^{-\gamma t}$ e imponemos $A(t) = \frac{A_0}{2}$:
$$
\frac{A_0}{2} = A_0 e^{-\gamma t} \implies \frac{1}{2} = e^{-\gamma t}
$$
Aplicamos logaritmo natural:
$$
-\ln(2) = -\gamma t \implies t = \frac{\ln(2)}{\gamma} = \frac{0,69315}{0,50\text{ s}^{-1}} \approx 1,39\text{ s}
$$

### (d) Amplitud después de $10$ oscilaciones

El tiempo transcurrido en $10$ oscilaciones es $t_{10} = 10 T_d = 10 (0,31426\text{ s}) = 3,1426\text{ s}$.
Evaluamos la función amplitud:
$$
A(t_{10}) = A_0 e^{-\gamma t_{10}} = (8,0\text{ cm}) e^{-(0,50\text{ s}^{-1})(3,1426\text{ s})} = (8,0\text{ cm}) e^{-1,5713} \approx (8,0\text{ cm})(0,2078) \approx 1,66\text{ cm}
$$

## Ejercicio 7

**Enunciado:**
La amplitud de un oscilador débilmente amortiguado disminuye $4\%$ en cada ciclo. Determine:
(a) La razón entre las amplitudes de dos máximos positivos sucesivos.
(b) La razón entre las energías mecánicas correspondientes a esos máximos.
(c) El porcentaje de energía mecánica perdido en cada ciclo.
(d) El decremento logarítmico $\delta = \ln\left(\frac{A_n}{A_{n+1}}\right)$.
(e) Estime el factor de calidad utilizando $Q \simeq \frac{\pi}{\delta}$.

**Resolución paso a paso:**

### (a) Razón entre amplitudes de dos máximos sucesivos

Si la amplitud disminuye un $4\%$ en cada ciclo, la nueva amplitud $A_{n+1}$ es el $96\%$ de la anterior $A_n$:
$$
A_{n+1} = (1 - 0,04) A_n = 0,96\, A_n
$$
Por lo tanto, la razón es:
$$
\frac{A_{n+1}}{A_n} = 0,96 \quad \left(\text{o bien } \frac{A_n}{A_{n+1}} = \frac{1}{0,96} \approx 1,0417\right)
$$

### (b) Razón entre las energías mecánicas correspondientes

Como la energía mecánica es proporcional al cuadrado de la amplitud ($E = \frac{1}{2}kA^2$):
$$
\frac{E_{n+1}}{E_n} = \left(\frac{A_{n+1}}{A_n}\right)^2 = (0,96)^2 = 0,9216
$$

### (c) Porcentaje de energía mecánica perdido en cada ciclo

$$
\text{Pérdida porcentual de } E = \left(1 - \frac{E_{n+1}}{E_n}\right) \times 100\% = (1 - 0,9216) \times 100\% = 0,0784 \times 100\% = 7,84\%
$$

### (d) Decremento logarítmico ($\delta$)

$$
\delta = \ln\left(\frac{A_n}{A_{n+1}}\right) = \ln\left(\frac{1}{0,96}\right) = -\ln(0,96) \approx 0,04082
$$

### (e) Estimación del factor de calidad ($Q$)

$$
Q \simeq \frac{\pi}{\delta} = \frac{\pi}{0,04082} \approx 76,96 \approx 77
$$

## Ejercicio 8

**Enunciado:**
En un experimento con un oscilador amortiguado de masa $m = 1,50\text{ kg}$, se observan dos máximos positivos consecutivos: $A_1 = 6,0\text{ cm}$, $A_2 = 5,0\text{ cm}$. El tiempo entre ambos máximos es $1,20\text{ s}$. Determine:
(a) La frecuencia angular amortiguada $\omega_d$.
(b) El coeficiente $\gamma$.
(c) El coeficiente de amortiguamiento $b$.
(d) La frecuencia angular natural $\omega_0$.
(e) La constante elástica $k$.

**Datos:**

* $m = 1,50\text{ kg}$
* $A_1 = 6,0\text{ cm}$
* $A_2 = 5,0\text{ cm}$
* Período amortiguado (tiempo entre máximos consecutivos): $T_d = 1,20\text{ s}$

**Resolución paso a paso:**

### (a) Frecuencia angular amortiguada ($\omega_d$)

$$
\omega_d = \frac{2\pi}{T_d} = \frac{2\pi}{1,20\text{ s}} = \frac{5\pi}{3}\text{ rad/s} \approx 5,236\text{ rad/s}
$$

### (b) Coeficiente $\gamma$

Sabemos que $A_2 = A_1 e^{-\gamma T_d}$, por lo tanto:
$$
\frac{A_1}{A_2} = e^{\gamma T_d} \implies \gamma T_d = \ln\left(\frac{A_1}{A_2}\right)
$$
Despejamos $\gamma$:
$$
\gamma = \frac{1}{T_d} \ln\left(\frac{A_1}{A_2}\right) = \frac{1}{1,20\text{ s}} \ln\left(\frac{6,0}{5,0}\right) = \frac{\ln(1,2)}{1,20} \approx \frac{0,18232}{1,20} \approx 0,1519\text{ s}^{-1}
$$

### (c) Coeficiente de amortiguamiento ($b$)

De la definición $\gamma = \frac{b}{2m}$:
$$
b = 2m\gamma = 2(1,50\text{ kg})(0,15193\text{ s}^{-1}) \approx 0,456\text{ N}\cdot\text{s/m}
$$

### (d) Frecuencia angular natural ($\omega_0$)

De $\omega_d = \sqrt{\omega_0^2 - \gamma^2}$, despejamos $\omega_0$:
$$
\omega_0 = \sqrt{\omega_d^2 + \gamma^2} = \sqrt{(5,2360)^2 + (0,1519)^2} = \sqrt{27,4156 + 0,0231} = \sqrt{27,4387} \approx 5,238\text{ rad/s}
$$

### (e) Constante elástica ($k$)

De $\omega_0^2 = \frac{k}{m}$:
$$
k = m \omega_0^2 = (1,50\text{ kg})(27,4387\text{ rad}^2/\text{s}^2) \approx 41,16\text{ N/m}
$$

## Ejercicio 9

**Enunciado:**
Un sistema de suspensión puede modelarse mediante una masa de $m = 300\text{ kg}$ y un resorte de constante $k = 1,80 \times 10^4\text{ N/m}$. Se desea que el sistema esté críticamente amortiguado. Determine:
(a) La frecuencia angular natural $\omega_0$.
(b) El valor del coeficiente de amortiguamiento crítico $b_c$.
(c) Si inicialmente $x_0 = 5,0\text{ cm}$ y $v_0 = 0$, obtenga la ecuación $x(t)$.
(d) Calcule el desplazamiento para $t = 0,50\text{ s}$.

**Datos:**

* $m = 300\text{ kg}$
* $k = 1,80 \times 10^4\text{ N/m} = 18000\text{ N/m}$
* $x_0 = 5,0\text{ cm} = 0,050\text{ m}$
* $v_0 = 0$

**Resolución paso a paso:**

### (a) Frecuencia angular natural ($\omega_0$)

$$
\omega_0 = \sqrt{\frac{k}{m}} = \sqrt{\frac{18000\text{ N/m}}{300\text{ kg}}} = \sqrt{60} \approx 7,746\text{ rad/s}
$$

### (b) Coeficiente de amortiguamiento crítico ($b_c$)

En el caso crítico, $\gamma = \omega_0$:
$$
b_c = 2m\omega_0 = 2(300\text{ kg})(7,7460\text{ rad/s}) \approx 4647,6\text{ N}\cdot\text{s/m} \approx 4,65 \times 10^3\text{ N}\cdot\text{s/m}
$$

### (c) Ecuación $x(t)$

Para un sistema críticamente amortiguado que parte del reposo desde una posición inicial $x_0$ (deducido en el Ejercicio 2):
$$
x(t) = x_0 e^{-\gamma t}(1 + \gamma t)
$$
Con $\gamma = \omega_0 = 7,75\text{ s}^{-1}$ y $x_0 = 0,050\text{ m}$ (o $5,0\text{ cm}$):
$$
x(t) = 0,050\, e^{-7,75 t}(1 + 7,75 t)\text{ m} \quad \left(\text{o en cm: } x(t) = 5,0\, e^{-7,75 t}(1 + 7,75 t)\text{ cm}\right)
$$

### (d) Desplazamiento para $t = 0,50\text{ s}$

Calculamos el producto $\gamma t$:
$$
\gamma t = (7,7460\text{ s}^{-1})(0,50\text{ s}) = 3,873
$$
Sustituimos en la ecuación de posición:
$$
x(0,50) = (0,050\text{ m}) e^{-3,873}(1 + 3,873) = (0,050\text{ m})(0,02080)(4,873) \approx 0,00507\text{ m} \approx 0,51\text{ cm}
$$

## Ejercicio 10

**Enunciado:**
Un oscilador débilmente amortiguado tiene $m = 1,0\text{ kg}$, $k = 100\text{ N/m}$, $b = 0,40\text{ N}\cdot\text{s/m}$. La amplitud inicial es $A_0 = 5,0\text{ cm}$. Determine:
(a) La frecuencia angular natural $\omega_0$.
(b) El factor de calidad $Q$.
(c) La razón entre dos amplitudes máximas consecutivas.
(d) La amplitud después de $10$ ciclos.
(e) La fracción de energía restante después de $10$ ciclos.

**Datos:**

* $m = 1,0\text{ kg}$
* $k = 100\text{ N/m}$
* $b = 0,40\text{ N}\cdot\text{s/m}$
* $A_0 = 5,0\text{ cm}$

**Resolución paso a paso:**

### (a) Frecuencia angular natural ($\omega_0$)

$$
\omega_0 = \sqrt{\frac{k}{m}} = \sqrt{\frac{100\text{ N/m}}{1,0\text{ kg}}} = \sqrt{100} = 10\text{ rad/s}
$$

### (b) Factor de calidad ($Q$)

1. Calculamos $\gamma$:
   $$
   \gamma = \frac{b}{2m} = \frac{0,40\text{ N}\cdot\text{s/m}}{2(1,0\text{ kg})} = 0,20\text{ s}^{-1}
   $$
2. Calculamos $\omega_d$:
   $$
   \omega_d = \sqrt{\omega_0^2 - \gamma^2} = \sqrt{10^2 - (0,20)^2} = \sqrt{99,96} \approx 9,998\text{ rad/s}
   $$
3. Calculamos $Q$:
   $$
   Q \simeq \frac{\omega_d}{2\gamma} = \frac{9,998\text{ rad/s}}{2(0,20\text{ s}^{-1})} \approx 24,995 \approx 25
   $$

### (c) Razón entre dos amplitudes máximas consecutivas

El período amortiguado es:
$$
T_d = \frac{2\pi}{\omega_d} = \frac{2\pi}{9,998\text{ rad/s}} \approx 0,6284\text{ s}
$$
La razón entre una amplitud y la anterior es:
$$
\frac{A_{n+1}}{A_n} = e^{-\gamma T_d} = e^{-(0,20\text{ s}^{-1})(0,6284\text{ s})} = e^{-0,12569} \approx 0,8819
$$
*(Nota: Si se toma $\frac{A_n}{A_{n+1}} = e^{0,12569} \approx 1,134$).*

### (d) Amplitud después de $10$ ciclos

Después de $N = 10$ ciclos ($t = 10 T_d$):
$$
A_{10} = A_0 e^{-\gamma (10 T_d)} = A_0 \left(e^{-\gamma T_d}\right)^{10}
$$
$$
A_{10} = (5,0\text{ cm}) e^{-10(0,12569)} = (5,0\text{ cm}) e^{-1,2569} \approx (5,0\text{ cm})(0,2845) \approx 1,42\text{ cm}
$$

### (e) Fracción de energía restante después de $10$ ciclos

Como $E \propto A^2$, la fracción de energía restante es:
$$
\frac{E_{10}}{E_0} = \left(\frac{A_{10}}{A_0}\right)^2 = \left(e^{-1,2569}\right)^2 = e^{-2,5138} \approx 0,0810 \quad (\text{o } 8,10\%)
$$