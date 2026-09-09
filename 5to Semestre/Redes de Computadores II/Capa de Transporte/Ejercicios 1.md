A continuación se presentan 5 ejercicios extraídos del **Capítulo 6: La Capa de Transporte** del libro _Redes de Computadoras_ (6ª edición) de Tanenbaum, copiados exactamente como se presentan en el texto, indicando la página del PDF en la que se encuentran y con su desarrollo explicado paso a paso1.

---

**Ejercicio 1: Problema 18**

**Página del PDF:** 6092

**Texto exacto del libro:**

**18.** Un cliente envía una petición de 128 bytes a un servidor situado a 100 km a través de una fibra óptica de 1 gigabit. Cuál es la eficiencia de la línea durante la llamada a procedimiento remoto?

**Desarrollo y respuesta:**

1. **Identificación de datos iniciales:**
    - Tamaño de la petición: $[M = 128\text{ bytes} = 128 \times 8 = 1024\text{ bits}]$.
    - Distancia física: $[d = 100\text{ km} = 100\,000\text{ m}]$.
    - Capacidad del canal: $[B = 1\text{ Gbps} = 10^9\text{ bits/s}]$.
    - Velocidad de propagación en la fibra óptica: $[v \approx 2 \times 10^8\text{ m/s}]$ (aproximadamente $[2/3]$ de la velocidad de la luz en el vacío)34.
2. **Cálculo del tiempo de transmisión (**$[t_{tx}]$**):** $[t_{tx} = \frac{\text{Tamaño del mensaje}}{\text{Ancho de banda}} = \frac{1024\text{ bits}}{10^9\text{ bits/s}} = 1,024 \times 10^{-6}\text{ s} = 1,024\ \mu\text{s}]$
3. **Cálculo del tiempo de propagación unidireccional (**$[t_{prop}]$**):** $[t_{prop} = \frac{\text{Distancia}}{\text{Velocidad de propagación}} = \frac{100\,000\text{ m}}{2 \times 10^8\text{ m/s}} = 5 \times 10^{-4}\text{ s} = 500\ \mu\text{s}]$
4. **Cálculo del tiempo total del ciclo RPC (**$[t_{total}]$**):** Una llamada a procedimiento remoto (RPC) requiere transmitir la petición y esperar la llegada de la respuesta. El tiempo de propagación de ida y vuelta (RTT) es $[2 \times t_{prop} = 1000\ \mu\text{s} = 1\text{ ms}]$.

Considerando el tiempo de emisión de la petición respecto al tiempo total del ciclo: $[t_{total} = t_{tx} + 2 \times t_{prop} = 1,024\ \mu\text{s} + 1000\ \mu\text{s} = 1001,024\ \mu\text{s}]$

1. **Cálculo de la eficiencia:** $[\text{Eficiencia} = \frac{t_{tx}}{t_{total}} = \frac{1,024\ \mu\text{s}}{1001,024\ \mu\text{s}} \approx 0,001023 \rightarrow \mathbf{0,1023\%}]$

_(Si se asume que el paquete de respuesta tiene también 128 bytes y el canal se utiliza durante ambas transmisiones, la eficiencia útil sería_ $[2 \times 1,024 / 1002,048 \approx 0,2044\%]$_)._

- **Respuesta:** La eficiencia de la línea durante la RPC es aproximadamente de $[0,1023\%]$ (o $[0,2044\%]$ contando la transmisión del mensaje de retorno).

---

**Ejercicio 2: Problema 32**

**Página del PDF:** 6105

**Texto exacto del libro:**

**32.** Considere el efecto de utilizar el arranque lento en una línea con un tiempo de ida y vuelta de 10 ms y sin congestión. La ventana de recepción es de 24 KB y el tamaño máximo del segmento es de 2 KB. ¿Cuánto tarda en enviarse la primera ventana completa?

**Desarrollo y respuesta:**

1. **Identificación de parámetros:**
    - Tiempo de ida y vuelta ($[RTT]$): $[10\text{ ms}]$.
    - Tamaño máximo de segmento ($[MSS]$): $[2\text{ KB}]$.
    - Ventana de recepción ($[rwnd]$): $[24\text{ KB}]$.
    - El número total de segmentos necesarios para completar la ventana receptora es $[24\text{ KB} / 2\text{ KB} = 12\text{ segmentos}]$.
2. **Evolución de la ventana de congestión (**$[cwnd]$**) durante el arranque lento:** En la fase de arranque lento (slow start), la ventana $[cwnd]$ comienza en $[1\text{ MSS}]$ ($[2\text{ KB}]$) y se duplica en cada $RTT$ completo al recibir las confirmaciones67:
    - **Ronda 1 (**$[t = 0\text{ a } 10\text{ ms}]$**):** Se envía $[1\text{ segmento}]$ ($[2\text{ KB}]$). Al cabo de $[10\text{ ms}]$ llegan las confirmaciones y $[cwnd]$ sube a $[2\text{ segmentos}]$ ($[4\text{ KB}]$).
    - **Ronda 2 (**$[t = 10\text{ a } 20\text{ ms}]$**):** Se envían $[2\text{ segmentos}]$ ($[4\text{ KB}]$). Al cabo de $[20\text{ ms}]$, $[cwnd]$ sube a $[4\text{ segmentos}]$ ($[8\text{ KB}]$).
    - **Ronda 3 (**$[t = 20\text{ a } 30\text{ ms}]$**):** Se envían $[4\text{ segmentos}]$ ($[8\text{ KB}]$). Al cabo de $[30\text{ ms}]$, $[cwnd]$ sube a $[8\text{ segmentos}]$ ($[16\text{ KB}]$).
    - **Ronda 4 (**$[t = 30\text{ a } 40\text{ ms}]$**):** Se envían $[8\text{ segmentos}]$ ($[16\text{ KB}]$). Al recibir los acuses a los $[40\text{ ms}]$, el límite de la ventana pasa a ser $[rwnd = 12\text{ segmentos}]$ ($[24\text{ KB}]$), ya que la ventana del receptor restringe el crecimiento ilimitado.
3. **Envío de la primera ventana completa:** A los $[t = 40\text{ ms}]$ (inicio de la Ronda 5), la ventana de transmisión alcanza por primera vez la capacidad máxima permitida de $[12\text{ segmentos}]$ ($[24\text{ KB}]$) y se envía la ventana completa.
4. **Respuesta:** Tarda $[40\text{ ms}]$ en empezar a enviarse la primera ventana completa de $[24\text{ KB}]$.

---

**Ejercicio 3: Problema 33**

**Página del PDF:** 6105

**Texto exacto del libro:**

**33.** Supongamos que la ventana de congestión TCP está fijada en 18 KB y se produce un timeout. ¿Qué tamaño tendrá la ventana si las cuatro siguientes ráfagas de transmisión se realizan correctamente? Supongamos que el tamaño máximo del segmento es de 1 KB.

**Desarrollo y respuesta:**

1. **Acción ante un timeout:** Cuando se produce un tiempo de espera agotado (timeout) estando la ventana de congestión en $[cwnd = 18\text{ KB}]$8:
    - El umbral de arranque lento ($[ssthresh]$) se establece a la mitad del valor actual: $[ssthresh = \frac{18\text{ KB}}{2} = 9\text{ KB}]$
    - La ventana de congestión ($[cwnd]$) se reinicia a $[1\text{ MSS} = 1\text{ KB}]$.
2. **Progreso tras 4 ráfagas de transmisión exitosas:**
    - **Ráfaga 1:** Se transmite con $[cwnd = 1\text{ KB}]$. Tras el RTT con éxito, $[cwnd]$ se duplica a $[2\text{ KB}]$ (modo arranque lento).
    - **Ráfaga 2:** Se transmite con $[cwnd = 2\text{ KB}]$. Tras el RTT con éxito, $[cwnd]$ se duplica a $[4\text{ KB}]$ (modo arranque lento).
    - **Ráfaga 3:** Se transmite con $[cwnd = 4\text{ KB}]$. Tras el RTT con éxito, $[cwnd]$ se duplica a $[8\text{ KB}]$ (modo arranque lento).
    - **Ráfaga 4:** Se transmite con $[cwnd = 8\text{ KB}]$. Al recibir las confirmaciones, la ventana intenta duplicarse a $[16\text{ KB}]$, pero alcanza el umbral $[ssthresh = 9\text{ KB}]$89. Al cruzar el umbral $[ssthresh]$, TCP abandona el arranque lento e ingresa a la fase de evitación de congestión (incremento aditivo), añadiendo $[1\text{ KB}]$ por RTT9. Por lo tanto, la ventana se incrementa hasta $[9\text{ KB} + 1\text{ KB} = 10\text{ KB}]$.
3. **Respuesta:** Tras las cuatro ráfagas exitosas, la ventana de congestión tendrá un tamaño de $[10\text{ KB}]$.

---

**Ejercicio 4: Problema 35**

**Página del PDF:** 61010

**Texto exacto del libro:**

**35.** Si el tiempo de ida y vuelta TCP, RTT, es actualmente de 30 ms y los siguientes acuses de recibo llegan después de 26, 32 y 24 ms, respectivamente, ¿cuál es la nueva estimación del RTT utilizando el algoritmo de Jacobson? Utilice α= 0. 9.

**Desarrollo y respuesta:**

1. **Fórmula del algoritmo de Jacobson para el tiempo de ida y vuelta suavisado (**$[SRTT]$**):** $[SRTT_{\text{nuevo}} = \alpha \cdot SRTT_{\text{anterior}} + (1 - \alpha) \cdot R]$11 donde $[\alpha = 0,9]$ y $[1 - \alpha = 0,1]$, siendo $[R]$ la muestra medida del RTT.
2. **Cálculo iterativo paso a paso:**
    - **Valor inicial:** $[SRTT_0 = 30\text{ ms}]$
    - **Primera muestra (**$[R_1 = 26\text{ ms}]$**):** $[SRTT_1 = (0,9 \times 30) + (0,1 \times 26) = 27 + 2,6 = 29,6\text{ ms}]$
    - **Segunda muestra (**$[R_2 = 32\text{ ms}]$**):** $[SRTT_2 = (0,9 \times 29,6) + (0,1 \times 32) = 26,64 + 3,2 = 29,84\text{ ms}]$
    - **Tercera muestra (**$[R_3 = 24\text{ ms}]$**):** $[SRTT_3 = (0,9 \times 29,84) + (0,1 \times 24) = 26,856 + 2,4 = 29,256\text{ ms}]$
3. **Respuesta:** La nueva estimación del RTT es de $[29,256\text{ ms}]$.

---

**Ejercicio 5: Problema 36**

**Página del PDF:** 61012

**Texto exacto del libro:**

**36.** Una máquina TCP está enviando ventanas completas de 65.535 bytes a través de un canal de 1 Gbps que tiene un retardo unidireccional de 10 ms. ¿Cuál es el rendimiento máximo alcanzable? ¿Cuál es la eficiencia de la línea?

**Desarrollo y respuesta:**

1. **Identificación de datos:**
    - Tamaña de la ventana de transmisión ($[W]$): $[65\,535\text{ bytes} = 65\,535 \times 8 = 524\,280\text{ bits}]$.
    - Capacidad del canal ($[B]$): $[1\text{ Gbps} = 10^9\text{ bits/s}]$.
    - Retardo de propagación unidireccional ($[t_{prop}]$): $[10\text{ ms} = 0,01\text{ s}]$.
    - Tiempo de ida y vuelta ($[RTT]$): $[2 \times 10\text{ ms} = 20\text{ ms} = 0,02\text{ s}]$.
2. **Cálculo del rendimiento máximo alcanzable (Throughput):** El rendimiento máximo está acotado por la cantidad de datos que se pueden transmitir por RTT1314: $[\text{Rendimiento} = \frac{\text{Ventana}}{RTT} = \frac{524\,280\text{ bits}}{0,02\text{ s}} = 26\,214\,000\text{ bits/s} \approx \mathbf{26,214\text{ Mbps}}]$
3. **Cálculo de la eficiencia de la línea:** La eficiencia mide la proporción del ancho de banda total del canal utilizada efectivamente: $[\text{Eficiencia} = \frac{\text{Rendimiento alcanzable}}{\text{Capacidad total del canal}} = \frac{26,214\text{ Mbps}}{1000\text{ Mbps}} = 0,026214 \rightarrow \mathbf{2,6214\%}]$
4. **Respuesta:** El rendimiento máximo alcanzable es de $[26,214\text{ Mbps}]$ y la eficiencia de la línea es del $[2,6214\%]$.