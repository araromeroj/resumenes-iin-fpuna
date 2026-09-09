Aquí tienes 5 ejercicios adicionales pertenecientes al **Capítulo 6: La Capa de Transporte** del libro _Redes de Computadoras_ (6ª edición) de Tanenbaum, copiados textualmente de las páginas del libro, indicando la página exacta del PDF y acompañados de su desarrollo explicado paso a paso.

---

**Ejercicio 1: Problema 7**

**Página del PDF:** 609

**Texto exacto del libro:**

**7.** Consideremos un protocolo de capa de transporte orientado a la conexión que utiliza un reloj con la hora del día para determinar los números de secuencia de los paquetes. El reloj utiliza un contador de 10 bits y marca una vez cada 125 mseg. La duración máxima de los paquetes es de 64 segundos. Si el emisor envía 4 paquetes por segundo, ¿cuánto tiempo podría durar la conexión sin entrar en la región prohibida?

**Desarrollo y respuesta:**

1. **Análisis de la frecuencia y periodo del reloj:**
    - Intervalo entre marcas del reloj: $125\text{ ms} = 0,125\text{ s}$.
    - Frecuencia del reloj: $\frac{1\text{ s}}{0,125\text{ s}} = 8\text{ marcas/segundo}$.
    - Capacidad del contador de 10 bits: $2^{10} = 1024$ valores posibles de número de secuencia.
    - Tiempo de ciclo/recorrido completo del reloj (wrap-around): $$T_{\text{ciclo}} = \frac{1024\text{ marcas}}{8\text{ marcas/s}} = 128\text{ segundos}$$
2. **Análisis de la tasa de emisión de paquetes:**
    - La velocidad de transmisión es de $R = 4\text{ paquetes/segundo}$.
    - Por cada segundo transcurrido, los números de secuencia consumidos por los paquetes aumentan a razón de $4\text{ unidades/s}$, mientras que el reloj avanza a razón de $8\text{ unidades/s}$.
3. **Evolución del espacio de secuencia y entrada en la región prohibida:**
    - A los $t = 128\text{ segundos}$, el reloj ha completado un ciclo entero de $1024$ marcas y reinicia su valor en $0$.
    - La frontera inferior de la región prohibida a los $t = 128\text{ s}$ queda definida por el tiempo de vida máximo del paquete ($T = 64\text{ segundos} = 64 \times 8 = 512\text{ marcas}$ por detrás del valor actual del reloj). Con el reloj de vuelta en $0$, la región prohibida abarca los números de secuencia en la zona $[-512, 0] \equiv \pmod{1024}$.
    - La secuencia de paquetes enviados habrá alcanzado para ese momento el valor: $$S(128) = 4\text{ paquetes/s} \times 128\text{ s} = 512$$
    - A los $t = 128\text{ segundos}$, la secuencia de paquetes alcanza exactamente el valor $512$, interseccionando con el límite inferior de la región prohibida del siguiente ciclo del reloj.
4. **Respuesta:** La conexión podrá durar un máximo de $128\text{ segundos}$ antes de entrar en la región prohibida.

---

**Ejercicio 2: Problema 15**

**Página del PDF:** 609

**Texto exacto del libro:**

**15.** Dos hosts envían simultáneamente datos a través de una red con una capacidad de 1 Mbps. El host A utiliza UDP y transmite un paquete de 100 bytes cada 1 mseg. El host B genera datos con una velocidad de 600 kbps y utiliza TCP. ¿Qué host obtendrá un mayor rendimiento?

**Desarrollo y respuesta:**

1. **Cálculo de la tasa de emisión del Host A (UDP):**
    - Tamaño del paquete: $100\text{ bytes} = 100 \times 8 = 800\text{ bits}$.
    - Frecuencia de envío: $1\text{ paquete}$ cada $1\text{ ms} = 1000\text{ paquetes/segundo}$.
    - Tasa requerida por UDP: $$\text{Tasa}_A = 800\text{ bits} \times 1000\text{ s}^{-1} = 800\,000\text{ bps} = 800\text{ kbps}$$
2. **Comportamiento ante la congestión:**
    - La demanda total sumada es $\text{Tasa}_A + \text{Tasa}_B = 800\text{ kbps} + 600\text{ kbps} = 1400\text{ kbps}$, la cual supera la capacidad del canal de $1\text{ Mbps} = 1000\text{ kbps}$.
    - Al producirse pérdida de paquetes por congestión, el **Host B (TCP)** reacciona reduciendo su ventana de congestión mediante la regla AIMD (disminución multiplicativa).
    - Por el contrario, **UDP no posee control de congestión**, por lo que el Host A continuará enviando a su tasa constante de $800\text{ kbps}$ sin autorregularse.
3. **Rendimiento efectivo alcanzado:**
    - Como UDP insiste en transmitir a $800\text{ kbps}$, acapara esa porción del ancho de banda.
    - TCP se repliega progresivamente y sólo puede aprovechar el ancho de banda sobrante no consumido por UDP: $$\text{Rendimiento}_B = 1000\text{ kbps} - 800\text{ kbps} = 200\text{ kbps}$$
4. **Respuesta:** El **Host A (UDP)** obtendrá un rendimiento significativamente mayor (aproximadamente $800\text{ kbps}$, frente a los $200\text{ kbps}$ que le quedarán al Host B).

---

**Ejercicio 3: Problema 34**

**Página del PDF:** 610

**Texto exacto del libro:**

**34.** Consideremos una conexión que utiliza TCP Reno. La conexión tiene un tamaño de ventana de congestión inicial de 1 KB, y un umbral inicial de 64. Supongamos que el incremento aditivo utiliza un tamaño de paso de 1 KB. ¿Cuál es el tamaño de la ventana de congestión en la ronda de transmisión 8, si la primera ronda de transmisión es la número 0?

**Desarrollo y respuesta:**

1. **Evolución en la fase de Arranque Lento (Slow Start):** Durante el arranque lento, mientras $\text{cwnd} < \text{ssthresh}$, la ventana de congestión se duplica en cada RTT (ronda de transmisión):
    - **Ronda 0:** $\text{cwnd}_0 = 1\text{ KB}$
    - **Ronda 1:** $\text{cwnd}_1 = 2\text{ KB}$
    - **Ronda 2:** $\text{cwnd}_2 = 4\text{ KB}$
    - **Ronda 3:** $\text{cwnd}_3 = 8\text{ KB}$
    - **Ronda 4:** $\text{cwnd}_4 = 16\text{ KB}$
    - **Ronda 5:** $\text{cwnd}_5 = 32\text{ KB}$
    - **Ronda 6:** $\text{cwnd}_6 = 64\text{ KB}$ (alcanza el umbral inicial $\text{ssthresh} = 64\text{ KB}$).
2. **Evolución en la fase de Evitación de Congestión (Aumento Aditivo):** A partir de $\text{cwnd} \ge \text{ssthresh}$, la ventana pasa a incrementarse linealmente añadiendo $1\text{ KB}$ por cada ronda de transmisión:
    - **Ronda 7:** $\text{cwnd}_7 = 64\text{ KB} + 1\text{ KB} = 65\text{ KB}$
    - **Ronda 8:** $\text{cwnd}_8 = 65\text{ KB} + 1\text{ KB} = 66\text{ KB}$
3. **Respuesta:** En la ronda de transmisión 8, la ventana de congestión tendrá un tamaño de $66\text{ KB}$.

---

**Ejercicio 4: Problema 47**

**Página del PDF:** 612

**Texto exacto del libro:**

**47.** Calcula el producto ancho de banda-retardo de las siguientes redes: (1) T1 (1,5 Mbps), (2) Ethernet (10 Mbps), (3) T3 (45 Mbps) y (4) STS-3 (155 Mbps). Supongamos un RTT de 100 ms. Recuerda que una cabecera TCP tiene 16 bits reservados para el tamaño de ventana. ¿Cuáles son sus implicaciones a la luz de tus cálculos?

**Desarrollo y respuesta:**

1. **Cálculo del Producto Ancho de Banda-Retardo (**$\text{BDP} = \text{Ancho de Banda} \times \text{RTT}$**) para** $\text{RTT} = 0,1\text{ s}$**:**
    - **(1) Red T1 (**$1,5\text{ Mbps}$**):** $$\text{BDP}_1 = 1,5 \times 10^6\text{ bps} \times 0,1\text{ s} = 150\,000\text{ bits} = \frac{150\,000}{8} = \mathbf{18\,750\text{ bytes}} \approx 18,75\text{ KB}$$
    - **(2) Ethernet (**$10\text{ Mbps}$**):** $$\text{BDP}_2 = 10 \times 10^6\text{ bps} \times 0,1\text{ s} = 1\,000\,000\text{ bits} = \frac{1\,000\,000}{8} = \mathbf{125\,000\text{ bytes}} \approx 125\text{ KB}$$
    - **(3) Red T3 (**$45\text{ Mbps}$**):** $$\text{BDP}_3 = 45 \times 10^6\text{ bps} \times 0,1\text{ s} = 4\,500\,000\text{ bits} = \frac{4\,500\,000}{8} = \mathbf{562\,500\text{ bytes}} \approx 562,5\text{ KB}$$
    - **(4) Red STS-3 (**$155\text{ Mbps}$**):** $$\text{BDP}_4 = 155 \times 10^6\text{ bps} \times 0,1\text{ s} = 15\,500\,000\text{ bits} = \frac{15\,500\,000}{8} = \mathbf{1\,937\,500\text{ bytes}} \approx 1,9375\text{ MB}$$
2. **Implicaciones respecto al tamaño de ventana TCP de 16 bits:**
    - La cabecera fija de TCP asigna 16 bits para el campo del tamaño de ventana de recepción, permitiendo una ventana máxima sin opciones de $2^{16} - 1 = 65\,535\text{ bytes} \approx 65,5\text{ KB}$.
    - Para la línea **T1** ($18,75\text{ KB}$), la ventana máxima sin opciones es suficiente para llenar el enlace.
    - Sin embargo, para **Ethernet** ($125\text{ KB}$), **T3** ($562,5\text{ KB}$) y **STS-3** ($1,9375\text{ MB}$), el producto ancho de banda-retardo sobrepasa por mucho los $65,5\text{ KB}$. Limitarse a $65,5\text{ KB}$ obligaría al emisor a quedarse inactivo esperando confirmaciones, desaprovechando la capacidad de la red.
3. **Conclusión:** Para aprovechar el rendimiento en redes de alta velocidad con retardo considerable (redes LFN), es **imprescindible utilizar la opción de escalado de ventana de TCP (Window Scale Option)**.

---

**Ejercicio 5: Problema 37**

**Página del PDF:** 610 (continuación en la pág. 611)

**Texto exacto del libro:**

**37.** ¿Cuál es la velocidad de línea más rápida a la que un host puede enviar cargas útiles TCP de 1.500 bytes con una duración máxima de paquete de 120 segundos sin tener que envolver los números de secuencia por ahí? Tenga en cuenta la sobrecarga TCP, IP y Ethernet. Suponga que las tramas Ethernet pueden enviarse continuamente.

**Desarrollo y respuesta:**

1. **Límite de secuencia de bytes de TCP:**
    - El número de secuencia en TCP utiliza $32\text{ bits}$, lo que representa un espacio máximo de $2^{32} = 4\,294\,967\,296\text{ bytes}$.
    - Para prevenir que los números de secuencia se repitan (wraparound) dentro del tiempo máximo de vida del paquete ($T_{\text{max}} = 120\text{ segundos}$), la tasa máxima de emisión de datos de carga útil debe ser: $$R_{\text{datos}} = \frac{2^{32}\text{ bytes}}{120\text{ s}} \approx 35\,791\,394,13\text{ bytes/s}$$
2. **Contabilidad de sobrecarga de protocolos:**
    - Carga útil TCP por segmento: $1500\text{ bytes}$.
    - Cabecera TCP: $20\text{ bytes}$.
    - Cabecera IP: $20\text{ bytes}$.
    - Trama Ethernet y capa física: $18\text{ bytes}$ de trama ($14\text{ MAC} + 4\text{ CRC}$) + $8\text{ bytes}$ (preámbulo/SFD) + $12\text{ bytes}$ de espacio intertrama (IFG) = $38\text{ bytes}$.
    - Tamaño total transmitido por la línea por paquete: $$\text{Tamaño total} = 1500 + 20 + 20 + 38 = 1578\text{ bytes}$$
3. **Cálculo de la velocidad de línea máxima:**
    - La tasa requerida en la línea física considerando la sobrecarga es: $$\text{Velocidad} = R_{\text{datos}} \times \left(\frac{1578\text{ bytes totales}}{1500\text{ bytes útiles}}\right) \times 8\text{ bits/byte}$$ $$\text{Velocidad} = 35\,791\,394,13 \times 1,052 \times 8 \approx 301\,212\,236\text{ bps} \approx \mathbf{301,21\text{ Mbps}}$$ _(Si se considera únicamente la sobrecarga de trama estándar sin IFG ni preámbulo,_ $1558\text{ bytes}$_, la velocidad resultante es aproximadamente_ $\mathbf{297,38\text{ Mbps}}$_)_.
4. **Respuesta:** La velocidad de línea máxima admisible es de aproximadamente $301,21\text{ Mbps}$ (o $297,38\text{ Mbps}$ según el modelo de sobrecarga de trama considerado).