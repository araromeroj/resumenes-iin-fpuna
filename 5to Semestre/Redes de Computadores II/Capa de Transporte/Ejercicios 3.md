A continuación presento una selección de ejercicios prácticos extraídos del Capítulo 6: La Capa de Transporte del libro *Redes de Computadoras* (6ª edición) de Tanenbaum. Se incluye un ejercicio por cada uno de los temas principales abordados en dicho capítulo, copiado textualmente del libro, indicando la página exacta del PDF y con su resolución paso a paso.

---

### Tema 1: Elementos de los Protocolos de Transporte (Direccionamiento y Espacio de Secuencia)

**Página del PDF:** 609  
**Ejercicio:** Problema 7  
**Texto exacto del libro:**  
7. Consideremos un protocolo de capa de transporte orientado a la conexión que utiliza un reloj con la hora del día para determinar los números de secuencia de los paquetes. El reloj utiliza un contador de 10 bits y marca una vez cada 125 mseg. La duración máxima de los paquetes es de 64 segundos. Si el emisor envía 4 paquetes por segundo, ¿Cuánto tiempo podría durar la conexión sin entrar en la región prohibida?

**Desarrollo y respuesta:**
* **Análisis de la frecuencia y capacidad del reloj:**
  * Intervalo entre marcas del reloj: $125\text{ ms} = 0{,}125\text{ s}$.
  * Frecuencia del reloj: $\frac{1\text{ s}}{0{,}125\text{ s}} = 8\text{ marcas/s}$.
  * Capacidad del contador de 10 bits: $2^{10} = 1024$ valores de número de secuencia.
  * Tiempo para completar un ciclo completo del reloj (*wrap-around*): $T_{\text{ciclo}} = \frac{1024\text{ marcas}}{8\text{ marcas/s}} = 128\text{ s}$.
* **Tasa de consumo de números de secuencia por los paquetes:**
  * El emisor transmite $4\text{ paquetes/s}$, consumiendo números de secuencia a esa velocidad.
  * Mientras el tiempo avanza, el reloj se incrementa a razón de $8\text{ unidades/s}$, mientras que los números de secuencia asignados a los paquetes avanzan a $4\text{ unidades/s}$.
* **Punto de colisión con la región prohibida:**
  * A los $t = 128\text{ s}$, el reloj completa su ciclo de 1024 marcas y se reinicia en $0$.
  * El límite inferior de la región prohibida tras el reinicio del reloj queda definido por el tiempo de vida máximo del paquete ($T = 64\text{ s} = 64 \times 8 = 512\text{ marcas}$ por detrás de la hora actual).
  * A los $t = 128\text{ s}$, el número de secuencia alcanzado por los paquetes emitidos es: $S(128) = 4\text{ paquetes/s} \times 128\text{ s} = 512$.
  * En ese instante exacto ($t = 128\text{ s}$), la secuencia del paquete alcanza el valor $512$, entrando justo en el límite de la región prohibida.
* **Respuesta:** La conexión puede durar un máximo de $128\text{ segundos}$ antes de entrar en la región prohibida.

---

### Tema 2: Protocolos de Transporte en Internet: UDP y RPC (Llamada a Procedimiento Remoto)

**Página del PDF:** 609  
**Ejercicio:** Problema 18  
**Texto exacto del libro:**  
18. Un cliente envía una petición de 128 bytes a un servidor situado a 100 km a través de una fibra óptica de 1 gigabit. ¿Cuál es la eficiencia de la línea durante la llamada a procedimiento remoto?

**Desarrollo y respuesta:**
* **Datos de entrada:**
  * Tamaño del mensaje de petición: $M = 128\text{ bytes} = 128 \times 8 = 1024\text{ bits}$.
  * Distancia física: $d = 100\text{ km} = 100{,}000\text{ m}$.
  * Capacidad del canal: $B = 1\text{ Gbps} = 10^9\text{ bits/s}$.
  * Velocidad de propagación en la fibra óptica: $v = 2 \times 10^8\text{ m/s}$.
* **Cálculo de tiempos:**
  * Tiempo de transmisión del mensaje de petición: $t_{\text{tx}} = \frac{1024\text{ bits}}{10^9\text{ bits/s}} = 1{,}024\ \mu\text{s}$.
  * Tiempo de propagación unidireccional: $t_{\text{prop}} = \frac{100{,}000\text{ m}}{2 \times 10^8\text{ m/s}} = 500\ \mu\text{s}$.
  * Tiempo de propagación de ida y vuelta (RTT): $\text{RTT} = 2 \times t_{\text{prop}} = 1000\ \mu\text{s}$.
* **Cálculo de la eficiencia:**
  * Tiempo total del ciclo RPC (transmisión + RTT): $t_{\text{total}} = t_{\text{tx}} + \text{RTT} = 1{,}024\ \mu\text{s} + 1000\ \mu\text{s} = 1001{,}024\ \mu\text{s}$.
  * Eficiencia de utilización del canal: $\text{Eficiencia} = \frac{t_{\text{tx}}}{t_{\text{total}}} = \frac{1{,}024}{1001{,}024} \approx 0{,}001023 \rightarrow \mathbf{0{,}1023\%}$. (Si se asume que la respuesta enviada por el servidor también es de 128 bytes y aprovecha el canal, la eficiencia útil transmitida en ambas direcciones sería $\frac{2 \times 1{,}024}{1002{,}048} \approx \mathbf{0{,}2044\%}$).
* **Respuesta:** La eficiencia de la línea durante la llamada RPC es de aproximadamente $0{,}1023\%$ (o $0{,}2044\%$ considerando la respuesta del servidor).

---

### Tema 3: TCP - Control de Flujo y Arranque Lento (Slow Start)

**Página del PDF:** 610  
**Ejercicio:** Problema 32  
**Texto exacto del libro:**  
32. Considere el efecto de utilizar el arranque lento en una línea con un tiempo de ida y vuelta de 10 ms y sin congestión. La ventana de recepción es de 24 KB y el tamaño máximo del segmento es de 2 KB. ¿Cuánto tarda en enviarse la primera ventana completa?

**Desarrollo y respuesta:**
* **Identificación de parámetros:**
  * Tiempo de ida y vuelta ($\text{RTT}$): $10\text{ ms}$.
  * Tamaño máximo de segmento ($\text{MSS}$): $2\text{ KB}$.
  * Ventana del receptor ($\text{rwnd}$): $24\text{ KB}$.
  * Capacidad total de la ventana en segmentos: $\frac{24\text{ KB}}{2\text{ KB}} = 12\text{ segmentos}$.
* **Evolución de la ventana de congestión ($\text{cwnd}$) durante el arranque lento:**
  * Ronda 1 ($t = 0\text{ ms}$): Se envía 1 segmento ($2\text{ KB}$). Al recibir los ACKs a los $10\text{ ms}$, $\text{cwnd}$ se duplica a 2 segmentos.
  * Ronda 2 ($t = 10\text{ ms}$): Se envían 2 segmentos ($4\text{ KB}$). Al recibir los ACKs a los $20\text{ ms}$, $\text{cwnd}$ se duplica a 4 segmentos.
  * Ronda 3 ($t = 20\text{ ms}$): Se envían 4 segmentos ($8\text{ KB}$). Al recibir los ACKs a los $30\text{ ms}$, $\text{cwnd}$ se duplica a 8 segmentos.
  * Ronda 4 ($t = 30\text{ ms}$): Se envían 8 segmentos ($16\text{ KB}$). Al recibir los ACKs a los $40\text{ ms}$, $\text{cwnd}$ se duplica a 16 segmentos, quedando acotado por el tamaño máximo de la ventana de recepción ($\text{rwnd} = 12\text{ segmentos}$ o $24\text{ KB}$).
* **Punto de envío de la primera ventana completa:**
  * A los $t = 40\text{ ms}$ (inicio de la Ronda 5), la ventana de transmisión alcanza por primera vez el límite de $12\text{ segmentos}$ ($24\text{ KB}$) y se envía la ventana completa.
* **Respuesta:** Tarda $40\text{ ms}$ en empezar a enviarse la primera ventana completa de $24\text{ KB}$.

---

### Tema 4: TCP - Gestión de Temporizadores y Estimación del RTT (Algoritmo de Jacobson)

**Página del PDF:** 610  
**Ejercicio:** Problema 35  
**Texto exacto del libro:**  
35. Si el tiempo de ida y vuelta TCP, RTT, es actualmente de 30 ms y los siguientes acuses de recibo llegan después de 26, 32 y 24 ms, respectivamente, ¿cuál es la nueva estimación del RTT utilizando el algoritmo de Jacobson? Utilice $\alpha = 0{,}9$.

**Desarrollo y respuesta:**
* **Fórmula del promedio móvil ponderado exponencialmente (EWMA) de Jacobson:**
  $$\text{SRTT}_{\text{nuevo}} = \alpha \cdot \text{SRTT}_{\text{anterior}} + (1 - \alpha) \cdot R$$
  donde $\alpha = 0{,}9$, $1 - \alpha = 0{,}1$ y $R$ es la muestra observada del RTT.
* **Cálculo iterativo paso a paso:**
  * Estimación inicial: $\text{SRTT}_0 = 30\text{ ms}$.
  * Muestra 1 ($R_1 = 26\text{ ms}$): $\text{SRTT}_1 = (0{,}9 \times 30) + (0{,}1 \times 26) = 27 + 2{,}6 = 29{,}6\text{ ms}$.
  * Muestra 2 ($R_2 = 32\text{ ms}$): $\text{SRTT}_2 = (0{,}9 \times 29{,}6) + (0{,}1 \times 32) = 26{,}64 + 3{,}2 = 29{,}84\text{ ms}$.
  * Muestra 3 ($R_3 = 24\text{ ms}$): $\text{SRTT}_3 = (0{,}9 \times 29{,}84) + (0{,}1 \times 24) = 26{,}856 + 2{,}4 = 29{,}256\text{ ms}$.
* **Respuesta:** La nueva estimación del RTT es de $29{,}256\text{ ms}$.

---

### Tema 5: TCP - Control de Congestión (Timeout, Umbral ssthresh y Algoritmo AIMD)

**Página del PDF:** 610  
**Ejercicio:** Problema 33  
**Texto exacto del libro:**  
33. Supongamos que la ventana de congestión TCP está fijada en 18 KB y se produce un timeout. ¿Qué tamaño tendrá la ventana si las cuatro siguientes ráfagas de transmisión se realizan correctamente? Supongamos que el tamaño máximo del segmento es de 1 KB.

**Desarrollo y respuesta:**
* **Consecuencias de un timeout por congestión:**
  * El umbral de arranque lento ($\text{ssthresh}$) se ajusta a la mitad del tamaño actual de la ventana: $\text{ssthresh} = \frac{18\text{ KB}}{2} = 9\text{ KB}$.
  * La ventana de congestión ($\text{cwnd}$) se reinicia al valor base de $1\text{ MSS} = 1\text{ KB}$.
* **Evolución durante las 4 ráfagas exitosas:**
  * Ráfaga 1: Transmite con $\text{cwnd} = 1\text{ KB}$. Al ser exitosa, en modo arranque lento se duplica a $2\text{ KB}$.
  * Ráfaga 2: Transmite con $\text{cwnd} = 2\text{ KB}$. Al ser exitosa, en modo arranque lento se duplica a $4\text{ KB}$.
  * Ráfaga 3: Transmite con $\text{cwnd} = 4\text{ KB}$. Al ser exitosa, en modo arranque lento se duplica a $8\text{ KB}$.
  * Ráfaga 4: Transmite con $\text{cwnd} = 8\text{ KB}$. Al recibir las confirmaciones, la ventana intenta duplicarse a $16\text{ KB}$, pero al alcanzar el umbral ($\text{ssthresh} = 9\text{ KB}$), TCP abandona el arranque lento e ingresa a la fase de evitación de congestión (incremento aditivo), añadiendo $1\text{ KB}$ lineal por RTT. Por consiguiente, la ventana se incrementa a $9\text{ KB} + 1\text{ KB} = 10\text{ KB}$.
* **Respuesta:** Tras las cuatro ráfagas exitosas, la ventana de congestión tendrá un tamaño de $10\text{ KB}$.

---

### Tema 6: Problemas de Rendimiento en Redes (Producto Ancho de Banda - Retardo y Límite de Ventana TCP)

**Página del PDF:** 612  
**Ejercicio:** Problema 47  
**Texto exacto del libro:**  
47. Calcula el producto ancho de banda-retardo de las siguientes redes: (1) T1 (1,5 Mbps), (2) Ethernet (10 Mbps), (3) T3 (45 Mbps) y (4) STS-3 (155 Mbps). Supongamos un RTT de 100 ms. Recuerda que una cabecera TCP tiene 16 bits reservados para el tamaño de ventana. ¿Cuáles son sus implicaciones a la luz de tus cálculos?

**Desarrollo y respuesta:**
* **Cálculo del Producto Ancho de Banda - Retardo ($\text{BDP} = \text{Ancho de banda} \times \text{RTT}$ con $\text{RTT} = 0{,}1\text{ s}$):**
  * (1) Red T1 ($1{,}5\text{ Mbps}$): $\text{BDP}_1 = 1{,}5 \times 10^6\text{ bps} \times 0{,}1\text{ s} = 150{,}000\text{ bits} = \frac{150{,}000}{8} = 18{,}750\text{ bytes} \approx 18{,}75\text{ KB}$.
  * (2) Ethernet ($10\text{ Mbps}$): $\text{BDP}_2 = 10 \times 10^6\text{ bps} \times 0{,}1\text{ s} = 1{,}000{,}000\text{ bits} = \frac{1{,}000{,}000}{8} = 125{,}000\text{ bytes} \approx 125\text{ KB}$.
  * (3) Red T3 ($45\text{ Mbps}$): $\text{BDP}_3 = 45 \times 10^6\text{ bps} \times 0{,}1\text{ s} = 4{,}500{,}000\text{ bits} = \frac{4{,}500{,}000}{8} = 562{,}500\text{ bytes} \approx 562{,}5\text{ KB}$.
  * (4) Red STS-3 ($155\text{ Mbps}$): $\text{BDP}_4 = 155 \times 10^6\text{ bps} \times 0{,}1\text{ s} = 15{,}500{,}000\text{ bits} = \frac{15{,}500{,}000}{8} = 1{,}937{,}500\text{ bytes} \approx 1{,}9375\text{ MB}$.
* **Implicaciones respecto al campo de ventana de 16 bits en la cabecera TCP:**
  * El campo del tamaño de ventana estándar de TCP posee 16 bits, lo que limita la ventana máxima sin opciones a $2^{16} - 1 = 65{,}535\text{ bytes} \approx 65{,}5\text{ KB}$.
  * Para la línea T1 ($18{,}75\text{ KB}$), una ventana de $65{,}5\text{ KB}$ resulta suficiente para mantener el canal saturado a plena capacidad.
  * Sin embargo, para Ethernet ($125\text{ KB}$), T3 ($562{,}5\text{ KB}$) y STS-3 ($1{,}9375\text{ MB}$), el BDP supera significativamente la capacidad de $65{,}5\text{ KB}$. Si el emisor se limita a esa ventana, pasará la mayor parte del tiempo inactivo esperando acuses de recibo, desaprovechando la mayor parte del ancho de banda disponible.
* **Respuesta:** En redes modernas de alta velocidad y alto retardo (redes LFN), es imprescindible utilizar la opción de escalado de ventana de TCP (*Window Scale Option*) para poder llenar la tubería de datos de la red.