Esta guía de estudio detalla los conceptos, procesos y características técnicas presentados en la **diapositiva 7** (correspondiente a los índices de fuentes a), integrando explicaciones profundas para la preparación de exámenes sobre la **Capa de Enlace de Datos**.

---

## 1. [[Piggybacking - superposición|El Concepto de Piggybacking (Superposición)]]

El **Piggybacking** (Superposición) es una técnica utilizada para optimizar el envío de confirmaciones en comunicaciones bidireccionales sobre un mismo enlace físico.

- **Proceso:** En lugar de enviar una trama de control dedicada únicamente para confirmar la recepción, el receptor espera un breve periodo para ver si tiene datos que enviar al origen. Si es así, incluye la confirmación en el encabezado de esa trama de datos saliente (en el campo de **ACK** - _Acknowledgement_ / Acuse de recibo).
- **Ventajas:**
    - **Uso eficiente del ancho de banda:** Reduce la cantidad de tramas pequeñas de control, dejando más espacio para los datos reales.
    - **Menor carga de procesamiento:** El receptor gestiona menos interrupciones al procesar una sola trama combinada en lugar de dos separadas.
- **Desventajas:**
    - **Gestión del tiempo:** Es complejo determinar cuánto tiempo exacto debe esperar la capa de enlace por un paquete de datos para "enganchar" el **ACK** (Acuse de recibo). Si espera demasiado, el emisor original podría sufrir un _timeout_ (agotamiento del temporizador) y retransmitir innecesariamente.

---

## 2. [[Automatic Repeat reQuest - ARQ|Control de Errores en Canales Ruidosos: Protocolo ARQ]]

En canales donde el ruido y las interferencias son comunes, se implementa el sistema **ARQ** (_Automatic Repeat reQuest_ - Solicitud de Repetición Automática) para añadir fiabilidad.

- **Mecanismos Fundamentales:**
    - **ACK (Acuse de Recibo):** El receptor debe confirmar obligatoriamente cada trama recibida correctamente.
    - **Temporizadores (Timers):** El emisor inicia un reloj al enviar una trama. Si el **ACK** (Acuse de recibo) no llega antes de que el reloj expire, la trama se reenvía.
    - **Numeración de Tramas y ACKs:** Es vital que tanto las tramas como las confirmaciones estén numeradas. De lo contrario, el receptor no podría distinguir si una trama entrante es una novedad o una retransmisión debida a un **ACK** (Acuse de recibo) perdido o retrasado.
    - **Protocolos Stop-and-Wait (Parada y Espera):** En su forma más simple, basta con un número de secuencia de 1 bit (alternando entre 0 y 1) para gestionar la comunicación.

---

## 3. [[Ventanas Corredizas|Conceptos de Ventanas Corredizas (Sliding Windows)]]

La **Ventana Corrediza** es una abstracción que permite al emisor tener múltiples tramas "en vuelo" (enviadas pero aún no confirmadas) para mejorar la eficiencia del enlace.

#### 3.1 La Ventana del Emisor

- **Definición:** Es el grupo de números de secuencia que el emisor tiene permitido enviar sin esperar un **ACK** (Acuse de recibo).
- **Funcionamiento:**
    - **Buffers:** El emisor debe guardar copias de todas las tramas dentro de la ventana en memorias intermedias por si se requiere una retransmisión.
    - **Movimiento:** El extremo inferior de la ventana avanza cuando llega un **ACK** (Acuse de recibo) válido. El extremo superior avanza a medida que la capa de red entrega nuevos paquetes para enviar.
    - **Tamaño:** Puede ser variable dependiendo del protocolo.

#### 3.2 La Ventana del Receptor

- **Definición:** Representa los números de secuencia de las tramas que el receptor está preparado para aceptar y almacenar en sus _buffers_ (memorias intermedias).
- **Características:**
    - Suele tener un tamaño fijo.
    - Avanza únicamente cuando entrega tramas ordenadas secuencialmente a la capa superior (capa de red).
    - **Importante:** Las ventanas de emisión y recepción no tienen que ser necesariamente del mismo tamaño.

---

## 4. Eficiencia y Canalización (Pipelining)

El uso de ventanas permite la canalización, lo que evita que el emisor se quede inactivo esperando confirmaciones en enlaces con retardos largos.

- **Bandwidth-Delay Product (BD - Producto Ancho de Banda-Retardo):** Es el cálculo que determina cuántas tramas "caben" en el cable físicamente.
    - $B$ (tramas/seg) = Tasa de datos / Longitud de la trama.
    - $Dp$ (seg) = Retardo de propagación.
- **Regla de Oro para el 100% de Utilización:** El tamaño de la ventana $W$ debe cumplir con: $W \ge 2BDp + 1$.

#### 4.1 Fórmulas de Eficiencia (Ef)

- **Con ACKs en tramas de control dedicadas:** $$Ef = \frac{W}{2 \cdot Dp \cdot B + 1}$$.
- **Con ACKs por Piggybacking (Superposición):** $$Ef = \frac{W}{2 \cdot Dp \cdot B + 2}$$.

---

## 5. Tipos de Protocolos de Ventana Deslizante

#### 5.1 Stop-and-Wait (Parada y Espera)

- **Tamaño de ventana:** Siempre es **1**.
- **Funcionamiento:** El emisor envía una trama y se bloquea hasta recibir el **ACK** (Acuse de recibo).
- **Escenarios:** La diapositiva muestra casos normales y anormales donde los números de secuencia evitan que una trama duplicada se confunda con una nueva.

#### 5.2 Go-Back-N (Retroceso-N)

- **Estrategia del Receptor:** La ventana del receptor es de tamaño **1**. Solo acepta tramas que lleguen en el orden exacto. Si llega la trama 4 pero falta la 3, descarta la 4 y todas las siguientes.
- **Estrategia del Emisor:** Al expirar el temporizador de la trama perdida, reenvía **todas** las tramas enviadas a partir de esa, aunque algunas hubieran llegado bien (pero fueron descartadas por el receptor).
- **Restricción de Tamaño:** Si el campo de secuencia tiene $k$ bits, el tamaño máximo de ventana es $MAX_SEQ = 2^k - 1$. Por ejemplo, con 3 bits ($k=3$), la ventana máxima es **7**.

#### 5.3 Selective Repeat (Repetición Selectiva)

- **Estrategia del Receptor:** La ventana es mayor a 1. El receptor acepta y guarda en _buffers_ tramas que lleguen fuera de orden mientras estén dentro de su ventana.
- **Mecanismos:**
    - **ACK Acumulativo:** Indica la trama más alta recibida en orden secuencial.
    - **NAK (Negative Acknowledgement - Acuse de Recibo Negativo):** Permite al receptor pedir específicamente la retransmisión de una sola trama que se perdió o dañó, sin reenviar el resto.
- **Características:** Es el más eficiente en el uso del ancho de banda, pero el más complejo de implementar debido a la gestión de memoria y temporizadores individuales por trama. $W_{max}=(MAXSEQ+1)/2$