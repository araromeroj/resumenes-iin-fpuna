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

---
## 6. Packet over SONET (Paquete sobre SONET)

Este concepto define el método estándar para transportar paquetes de datos, principalmente **IP** (Internet Protocol - Protocolo de Internet), a través de infraestructuras de fibra óptica de alta velocidad.

- **Mecanismo de transporte:** Se utiliza el protocolo **PPP** (Point-to-Point Protocol - Protocolo Punto a Punto) para realizar el entramado de los paquetes dentro de la carga útil de **SONET** (Synchronous Optical NETwork).
- **Aplicación práctica:** Estos enlaces son fundamentales en las **WAN** (Wide Area Network - Red de Área Amplia) para interconectar routers de **ISP** (Internet Service Provider - Proveedor de Servicios de Internet) a distancias considerables.
- **Sincronización:** Dado que **SONET** (Synchronous Optical NETwork) es un sistema síncrono, las tramas se emiten de forma continua cada 125 microsegundos, incluso si no hay datos de usuario que enviar, utilizando datos ficticios para mantener el flujo.

---

## 7. Protocolo PPP (Point-to-Point Protocol - Protocolo Punto a Punto)

Es el protocolo más utilizado en Internet para establecer conexiones directas entre dos nodos a través de líneas punto a punto.

### 7.1 Origen y Características

- **Herencia:** Se basa en una evolución de los protocolos **HDLC** (High-level Data Link Control - Control de Enlace de Datos de Alto Nivel) y **SLIP** (Serial Line Internet Protocol - Protocolo de Internet de Línea Serial).
- **Funciones Principales:**
    1. **Entramado:** Define un método de delimitación de tramas no ambiguo que incluye la detección de errores mediante campos de verificación.
    2. **LCP (Link Control Protocol - Protocolo de Control de Enlace):** Se encarga de activar, probar, negociar opciones y desactivar la línea de comunicación.
    3. **NCP (Network Control Protocol - Protocolo de Control de Red):** Permite negociar parámetros específicos de la capa de red de forma independiente al protocolo utilizado (como la asignación de direcciones **IP**).

### 7.2 Capacidades Técnicas

El protocolo permite la configuración dinámica de enlaces, autenticación de las partes, compresión de los encabezados de los paquetes, verificación de la calidad del enlace y control de errores. Además, soporta **Multilink** (Multienlace), permitiendo combinar varias conexiones físicas en una sola interfaz lógica.

---

## 8. Formato de la Trama PPP

El formato está diseñado para ser orientado a bytes, lo que significa que todas las tramas tienen una longitud que es múltiplo de un byte de 8 bits.

- **Campos de la trama:**
    - **Flag (Bandera):** Inicia y finaliza la trama con el valor binario `01111110` (0x7E en hexadecimal).
    - **Address (Dirección):** Siempre se establece en `11111111` para indicar que todas las estaciones deben aceptar la trama, lo que evita la necesidad de asignar direcciones físicas individuales.
    - **Control:** Su valor por defecto es `00000011`, indicando una trama no numerada en el modo más común de operación.
    - **Protocol (Protocolo):** Indica qué tipo de paquete viaja en la carga útil (ej. **IPv4**, **IPv6**, o mensajes de control como **LCP**).
    - **Payload (Carga útil):** Campo de longitud variable que contiene los datos transmitidos.
    - **Checksum (Suma de comprobación):** Un campo de 2 o 4 bytes para detectar errores de transmisión.
- **Relleno de Bytes (Byte Stuffing):** Si el valor del byte de bandera aparece dentro de los datos, se inserta un byte de **Escape** (Escape) `0x7D` para evitar confusiones en la delimitación de la trama.
- **Scrambling (Mezclado):** Antes de enviarse a través de **SONET**, los datos se procesan con una función **XOR** (OR exclusivo) para asegurar que haya suficientes transiciones de bits, lo cual es necesario para mantener la sincronización del reloj en el receptor.

---

## 9. Diagrama de Estados de PPP

El enlace pasa por varias fases críticas desde que se detecta la portadora física hasta que se cierra la sesión.

1. **DEAD (Muerto):** Fase inicial donde no existe una conexión física activa.
2. **ESTABLISH (Establecer):** Los nodos intercambian paquetes **LCP** (Link Control Protocol - Protocolo de Control de Enlace) para acordar las opciones del enlace.
3. **AUTHENTICATE (Autenticar):** Fase opcional donde las dos partes verifican su identidad.
4. **NETWORK (Red):** Se utilizan paquetes **NCP** (Network Control Protocol - Protocolo de Control de Red) para configurar el protocolo de capa de red (como asignar una dirección **IP** temporal).
5. **OPEN (Abierto):** Estado en el que el transporte de datos de usuario tiene lugar.
6. **TERMINATE (Terminar):** Fase de cierre de la conexión para liberar recursos.