## Resumen Ejecutivo

La capa de enlace de datos actúa como el puente crítico entre la capa de red y la capa física, transformando un canal de transmisión crudo en una línea que parece libre de errores de transmisión. Su unidad fundamental de información es la **trama**. Las responsabilidades principales de esta capa incluyen el entramado (framing), la gestión de errores mediante redundancia, el control de flujo para evitar la saturación del receptor y el direccionamiento físico. El análisis destaca que la elección de servicios (con o sin conexión/confirmación) y los métodos de detección/corrección de errores (como la Distancia de Hamming y códigos convolucionales) dependen directamente de la calidad del medio físico y la tasa de errores esperada.

--------------------------------------------------------------------------------

## 1. Definición y Funciones Principales

La capa de enlace de datos es la responsable del envío de tramas de información en un enlace simple (siguiente salto). Su funcionamiento consiste en aceptar paquetes de la capa de red, encapsularlos en tramas para su envío a través de la capa física y realizar el proceso inverso en la recepción.

### Objetivos de Diseño

- **Interfaz de servicio definida:** Proveer una conexión clara con la capa de red.
- **Entramado (Framing):** Identificar y delimitar tramas dentro de una secuencia de bytes como segmentos autocontenidos.
- **Gestión de errores:** Detectar y, en ciertos casos, corregir errores derivados del ruido, la distorsión y la atenuación.
- **Control de flujo:** Regular la velocidad de transmisión para que emisores rápidos no sobrepasen a receptores lentos.
- **Direccionamiento físico:** Identificar el inicio y el fin del enlace de datos.

--------------------------------------------------------------------------------

## 2. Servicios Proporcionados a la Capa de Red

El servicio principal es la transferencia de datos desde la capa de red del host transmisor hacia la capa de red del host receptor. Existen tres categorías principales de servicios según la fiabilidad requerida:

| **Tipo de Servicio**                       | **Características**                                                       | **Aplicación Típica** |
| ------------------------------------------ | ------------------------------------------------------------------------- | --------------------- |
| *Sin conexión y sin confirmación*          | Apropiado para medios con tasas de error muy bajas.                       | Ethernet              |
| *Sin conexión y con confirmación*          | Necesario en canales inestables o donde la tasa de errores es importante. | Redes Wi-Fi           |
| *Orientado a la conexión con confirmación* | Garantiza el orden y la recepción única mediante numeración de tramas.    | Redes WAN             |

--------------------------------------------------------------------------------

## 3. Métodos de Entramado (Framing)

Para que el receptor reconozca el inicio y el fin de una trama, se emplean diversos métodos de identificación:

1. **Conteo de caracteres (o bytes):** Un campo al inicio indica la longitud. Su principal desventaja es la alta probabilidad de perder el sincronismo si el conteo se corrompe.
2. **Relleno de bytes (Byte Stuffing):** Utiliza bytes de "Bandera" (Flag) para delimitar. Si el dato contiene un byte igual a la bandera, se inserta un byte de "Escape" (ESC) para evitar confusiones. Es común en protocolos orientados a caracteres.
3. **Relleno de bits (Bit Stuffing):** Emplea una secuencia específica (ej. `01111110`) como bandera. Si aparecen cinco "1" seguidos en los datos, se inserta un "0" automáticamente, el cual es eliminado por el receptor (destuffing).
4. **Violación de la codificación física:** Utiliza señales no válidas en la codificación de la capa física (como la falta de inversión de polaridad en Manchester) para marcar límites.

--------------------------------------------------------------------------------

## 4. Control de Flujo

El objetivo es limitar el ritmo de envío para que el receptor pueda procesar la información. Se clasifican en dos mecanismos:

- **Basado en retroalimentación:** El receptor envía información explícita al emisor (permisos o estado de fase). Un ejemplo clásico son las **ventanas deslizantes**.
- **Basado en tasas de bits:** El protocolo limita intrínsecamente la velocidad de transmisión mediante mecanismos definidos, sin requerir feedback constante del receptor.

--------------------------------------------------------------------------------

## 5. Detección y Corrección de Errores

Los errores son causados principalmente por ruido térmico (errores uniformes) o ruidos impulsivos (errores de ráfaga). La estrategia fundamental es añadir **redundancia estructurada** al mensaje original.

### Conceptos Fundamentales

- **Palabra codificada (Codeword):** Mensaje original de m bits + r bits de redundancia = n bits totales.
- **Distancia de Hamming:** Cantidad mínima de bits que deben cambiar para transformar una palabra codificada válida en otra válida.

### Capacidades según la Distancia de Hamming (d_{min})

- **Para detectar** **s** **errores:** Se requiere que $d_{min} > s$.
- **Para corregir** **t** **errores:** Se requiere que $d_{min} > 2t$.

### Tipos de Códigos

1. **Códigos de Detección:** Utilizan menos bits de redundancia. Incluyen bits de paridad, Checksums y CRC (Cíclicos).
2. **Códigos de Corrección (FEC - Forward Error Correction):** Poseen suficiente redundancia para que el receptor deduzca el mensaje correcto.
    - **Código de Hamming:** Para corregir errores de un solo bit, se debe cumplir la relación $m + r + 1 \leq 2^r$. Utiliza sumas de paridad sobre subconjuntos de la palabra para generar un "síndrome" que indica la posición del error.
    - **Códigos Convolucionales:** La salida es una función de los bits actuales y anteriores. Son decodificados mediante el **Algoritmo de Viterbi**. Un ejemplo es el código binario de la NASA (tasa 1/2) utilizado en el estándar IEEE 802.11.

--------------------------------------------------------------------------------

## Conclusiones Técnicas

El diseño de la capa de enlace debe equilibrar la eficiencia (poca redundancia) con la fiabilidad (detección/corrección robusta). Mientras que en medios estables como Ethernet se opta por servicios sencillos sin confirmación, en medios volátiles como el inalámbrico o enlaces de larga distancia (WAN), es imperativo el uso de confirmaciones, retransmisiones y códigos de control de errores más complejos para garantizar la integridad de los datos entregados a la capa de red.

---
# Cuestrionario
Responda brevemente a las siguientes preguntas basándose en el contenido anterior.

1. **¿Cuál es la función principal de la capa de enlace de datos en relación con la capa física y la capa de red?**
	La capa de enlace actúa como responsable del envío de tramas a través de un enlace simple, manejando errores y regulando el flujo de datos. Su función es aceptar paquetes de la capa de red y entregarlos a la capa física para su transporte.
2. **Explique la diferencia entre un paquete y una trama.**
	Un paquete es la unidad de datos que proviene de la capa de red, mientras que una trama es el resultado de encapsular ese paquete con un encabezado y un tráiler específicos para su transmisión en la capa de enlace.
3. **¿En qué situaciones es preferible utilizar un servicio sin conexión y con confirmación de recepción?**
	Este servicio es apropiado cuando la tasa de errores del canal es importante o cuando se trabaja con canales inestables. Un ejemplo común de su aplicación son las redes Wi-Fi.
4. **¿Cuál es la principal desventaja del método de entramado por conteo de caracteres?**
	La mayor desventaja es que se puede perder el sincronismo fácilmente si el campo de longitud de la trama se altera durante la transmisión. Por esta razón, suele utilizarse en combinación con otros métodos.
5. **Describa brevemente cómo funciona el relleno de bits (bit stuffing).**
	El relleno de bits consiste en insertar bits adicionales en la secuencia de datos para asegurar que los patrones de bits de los datos no sean confundidos con las banderas que marcan el inicio o el fin de la trama.
6. **¿Qué factores físicos provocan usualmente los errores de transmisión en las tramas?**
	Los errores de datos se originan principalmente por fenómenos de ruido (térmico o impulsivo), distorsión de la señal y atenuación durante el recorrido por el medio físico.
7. **¿Qué es la redundancia en el contexto del control de errores?**
	La redundancia consiste en añadir bits adicionales (bits de control o verificación) al mensaje original de longitud m. Estos bits permiten que el receptor detecte o corrija alteraciones en la información transmitida.
8. **Defina el concepto de Distancia de Hamming.**
	Es la cantidad mínima de bits que deben ser cambiados para pasar de una palabra codificada válida a otra cualquiera dentro de un código específico. Determina la capacidad de detección y corrección del código.
9. **¿Cuál es la diferencia fundamental entre el control de flujo basado en retroalimentación y el basado en tasas?**
	El control por retroalimentación requiere que el receptor envíe información al emisor dándole permiso para transmitir. El control basado en tasas limita la velocidad mediante mecanismos internos del protocolo sin requerir feedback constante.
10. **¿Qué algoritmo se utiliza comúnmente para decodificar bits en códigos convolucionales?**
	Se utiliza el "Algoritmo de Viterbi". Este es fundamental para procesar códigos convolucionales, como los utilizados por la NASA o en el estándar IEEE 802.11.
