### Tema 1: Eficiencia y Potencia en la Capa de Transporte (Métrica de Kleinrock)

#### Desarrollo teórico

En el diseño de protocolos de la capa de transporte y en los mecanismos de control de congestión, la optimización del rendimiento requiere equilibrar dos métricas contrapuestas: la velocidad de transferencia (_throughput_ o carga aceptada por la red) y el tiempo de tránsito (_delay_ o retardo total).

A medida que una entidad de transporte incrementa la carga instalada ($\lambda$), el _throughput_ crece de manera casi lineal mientras los conmutadores y enrutadores mantengan sus colas con baja ocupación. Sin embargo, al aproximarse a la capacidad del canal ($C$), los búferes comienzan a llenarse, provocando un aumento exponencial del retardo de cola. Si la carga sobrepasa la capacidad, los búferes se desbordan, se descartan paquetes y la red entra en colapso por congestión (_congestion collapse_).

  

Para calcular el punto de operación óptimo (el "codo" o _knee_ de la curva de retardo/carga), Leonard Kleinrock (1979) definió formalmente la métrica de **Potencia** (_Power_):

  

$$\text{Potencia} = \frac{\text{Carga}}{\text{Retardo}}$$

- **Comportamiento de la función**:
    
      
    1. Con cargas bajas, el retardo se mantiene relativamente constante (determinado por el tiempo de transmisión y la propagación física). La potencia aumenta linealmente conforme se incrementa la carga.
        
          
        
    2. Alcanza su valor máximo en la carga donde la derivada del retardo respecto a la carga empieza a crecer más rápido que el incremento proporcional del _throughput_.
        
          
        
    3. Al sobrepasar este punto de carga óptima, el retardo aumenta exponencialmente, provocando que la potencia caiga bruscamente hacia cero.
        
          
        

La carga con la potencia más alta representa la tasa de inyección eficiente que la entidad de transporte debe colocar en la red para maximizar la utilización sin saturar los búferes intermedios.

  

#### Ejemplo práctico

Considere una autopista con una caseta de cobro. Si circula solo un vehículo por minuto, la vía está despejada y el tiempo de viaje es mínimo (10 minutos), pero la capacidad de la carretera está desaprovechada (carga baja, potencia baja). Si ingresan 100 vehículos por minuto, la carretera se utiliza a su capacidad ideal y el tiempo aumenta marginalmente a 11 minutos (punto de máxima potencia). Si ingresan 1,000 vehículos por minuto, se forma un embotellamiento masivo y el tiempo de viaje sube a 180 minutos; aunque pasen muchos autos, el retardo destruye la eficiencia de la vía y la potencia cae casi a cero.

  

#### Glosario de siglas

- `QoS - Quality of Service: Calidad de Servicio`
    
      
    

### Tema 2: Equidad Máxima-Mínima (_Max-Min Fairness_)

#### Desarrollo teórico

Cuando múltiples entidades de transporte compiten por el ancho de banda disponible a través de una topología de red con rutas heterogéneas, se requiere un criterio formal para distribuir el recurso sin favorecer ni perjudicar arbitrariamente a ningún flujo.

  

El principio de **Equidad Máxima-Mínima** (_Max-Min Fairness_) establece que una asignación de ancho de banda a un conjunto de flujos es equitativa si no es posible aumentar la asignación de un flujo sin disminuir simultáneamente la asignación de otro flujo que ya recibe una tasa igual o menor.

  

- **Propiedades e implicaciones de arquitectura**:
    
      
    1. Da prioridad a la satisfacción de los flujos más restringidos o con demandas menores.
        
          
        
    2. Evita la inanición (_starvation_) de flujos que atraviesan múltiples saltos frente a flujos de un solo enlace.
        
          
        
    3. **Algoritmo de asignación**:
        
          
        - Se identifican los recursos compartidos (enlaces).
            
              
            
        - Se asigna en partes iguales la capacidad del enlace más restringido (enlace cuello de botella) entre todos los flujos no satisfechos que cruzan por él.
            
              
            
        - Si un flujo requiere menos ancho de banda que su cuota equitativa, recibe lo exigido y el sobrante se redistribuye equitativamente entre los flujos restantes.
            
              
            

#### Ejemplo práctico

Suponga un enlace de $10\text{ Mbps}$ compartido por tres conexiones de transporte: $A$, $B$ y $C$. El emisor $A$ requiere únicamente $2\text{ Mbps}$ debido a restricciones en su propia interfaz. Con equidad máxima-mínima, a $A$ se le asignan sus $2\text{ Mbps}$ completos. Los $8\text{ Mbps}$ restantes del enlace se dividen por igual entre $B$ y $C$, otorgando $4\text{ Mbps}$ a cada uno. Esto es superior a una división ciega de $3.33\text{ Mbps}$ por usuario, la cual desperdiciaría $1.33\text{ Mbps}$ en $A$ que este no puede utilizar.

  

#### Glosario de siglas

- `Mbps - Megabits per second: Megabits por segundo`
    
      
    

### Tema 3: Protocolo de Datagramas de Usuario (UDP)

#### Desarrollo teórico

El protocolo UDP (_User Datagram Protocol_) es un protocolo no orientado a conexión perteneciente a la capa de transporte del modelo TCP/IP (RFC 768). UDP proporciona un mecanismo simplificado para enviar datagramas IP encapsulados sin necesidad de establecer una conexión previa ni mantener un estado de la sesión en los extremos.

  

#### Mecanismos omitidos por diseño (Lo que UDP NO hace)

1. **Sin Control de Flujo**: UDP no implementa mecanismos de ventana ni acuses de recibo para regular la velocidad de envío en función de la capacidad de procesamiento del receptor.
    
      
    
2. **Sin Control de Congestión**: UDP no monitorea el estado de saturación de la red ni reacciona ante la pérdida de paquetes reduciendo la tasa de envío.
    
      
    
3. **Sin Retransmisión (Sin fiabilidad garantizada)**: UDP no utiliza temporizadores ni números de secuencia para retransmitir datagramas perdidos, duplicados o desordenados. Si un paquete se corrompe o se descarta en un enrutador intermedio, UDP simplemente lo desecha.
    
      
    

#### Valor principal y funciones de UDP

- **Multiplexación/Desmultiplexación mediante Puertos**: Ofrece una interfaz abstracta hacia la capa IP permitiendo que múltiples procesos de usuario en la misma máquina compartan la red identificándose mediante números de puerto de origen y destino de 16 bits.
    
      
    
- **Verificación Opcional de Errores**: Incluye una suma de comprobación (_checksum_) de 16 bits opcional en IPv4 (obligatoria en IPv6) que abarca la cabecera UDP, la carga útil y una pseudocabecera IP para verificar la integridad de extremo a extremo.
    
      
    

#### Ventajas y Desventajas

|**Ventajas**|**Desventajas**|
|---|---|
|**Simplicidad**: Sin establecimiento de conexión (sin _handshake_ de 3 vías), lo que elimina la latencia inicial.|**Falta de fiabilidad**: Pérdida de paquetes no detectada ni corregida por el protocolo.|
|**Baja sobrecarga (_Low Overhead_)**: Cabecera reducida de solo 8 bytes (comparada con los 20 bytes mínimos de TCP).|**Inexistencia de control de flujo**: Riesgo de saturar el búfer del receptor.|
|**Control preciso sobre el tiempo de envío**: Los datos se entregan inmediatamente a la capa IP tan pronto como la aplicación los genera.|**Ausencia de control de congestión**: Puede provocar colapso en la red si no se controla en la capa de aplicación.|

#### Aplicaciones reales

- **Consultas Cliente-Servidor Breves**: DNS (_Domain Name System_), donde el costo de establecer una conexión TCP supera el tiempo de transferencia de los datos y una pérdida se resuelve reordenando una consulta completa tras un tiempo límite.
    
      
    
- **Transmisión de Medios en Tiempo Real (Streaming/VoIP)**: Donde la latencia mínima es crítica y perder algunos fotogramas o muestras de audio es preferible a sufrir retardo por retransmisiones.
    
      
    
- **Juegos en Línea Multijugador**: Requieren actualización constante de estados en tiempo real con la menor latencia posible.
    
      
    

#### Ejemplo práctico

En una llamada de Voz sobre IP (VoIP), si un paquete que contiene $20\text{ ms}$ de audio se pierde en la red, es inútil retransmitirlo $150\text{ ms}$ después porque la conversación ya habrá avanzado y reproducir el paquete tarde generaría un chasquido molesto o eco. UDP permite enviar el fragmento inmediatamente; si se pierde, el códec de audio disimula la pequeña brecha sin detener el flujo conversacional.

  

#### Glosario de siglas

- `UDP - User Datagram Protocol: Protocolo de Datagramas de Usuario`
    
      
    
- `TCP - Transmission Control Protocol: Protocolo de Control de Transmisión`
    
      
    
- `IP - Internet Protocol: Protocolo de Internet`
    
      
    
- `RFC - Request for Comments: Petición de Comentarios`
    
      
    
- `DNS - Domain Name System: Sistema de Nombres de Dominio`
    
      
    
- `VoIP - Voice over Internet Protocol: Voz sobre Protocolo de Internet`
    
      
    

### Tema 4: Llamada a Procedimiento Remoto (RPC)

#### Desarrollo teórico

La **Llamada a Procedimiento Remoto** (_Remote Procedure Call_ - RPC) es un mecanismo de abstracción de alto nivel construido habitualmente sobre UDP (o TCP) que permite a un programa ejecutar un procedimiento o función en un servidor remoto de manera transparente, simulando una llamada a función local.

  

- **Componentes y Operación**:
    
      
    1. **Proceso Cliente**: Llama a un procedimiento local especial denominado _client stub_ (talón o muñón del cliente) pasando los parámetros convencionales.
        
          
        
    2. **Client Stub**: Empaqueta los parámetros de la llamada en un formato estándar independiente de la arquitectura de la máquina (proceso denominado _marshalling_ o empaquetado) y construye un mensaje de red.
        
          
        
    3. **Envío por Capa de Transporte**: El _stub_ envía el mensaje al servidor mediante un socket de transporte (usualmente sobre UDP por su rapidez).
        
          
        
    4. **Server Stub**: El _stub_ en el servidor recibe el mensaje, desempaqueta los parámetros (_unmarshalling_) y llama a la función o procedimiento real en la máquina servidor.
        
          
        
    5. **Respuesta**: La función del servidor devuelve los resultados al _server stub_, el cual los empaqueta y retransmite al _client stub_, que desempaca el resultado y lo retorna al proceso cliente que estaba bloqueado esperando.
        
          
        
- **Semánticas de Ejecución ante Fallos**:
    
    Debido a que los mensajes pueden perderse o duplicarse cuando se usa UDP, RPC debe definir semánticas de control de fallos:
    
      
    - **Al menos una vez (_At-least-once_)**: Se reintenta el envío hasta obtener respuesta; adecuado para operaciones idempotentes (operaciones que no alteran el estado si se ejecutan múltiples veces, ej. leer un archivo).
        
          
        
    - **A lo sumo una vez (_At-most-once_)**: Evita la ejecución repetida de operaciones no idempotentes (ej. debitar un saldo bancario) utilizando números de secuencia y registros de historial en el servidor.
        
          
        
    - **Exactamente una vez (_Exactly-once_)**: El caso ideal, pero técnicamente imposible de garantizar en presencia de fallos arbitrarios de red y caídas de nodos sin suposiciones de consenso estrictas.
        
          
        

#### Ejemplo práctico

Considere un sistema de archivos distribuido NFS (_Network File System_). Un usuario en su computadora cliente abre un archivo alojado en un servidor remoto mediante la llamada `read(fd, buffer, nbytes)`. El _stub_ cliente de RPC atrapa la función `read()`, empaqueta los identificadores y los envía por UDP al servidor de archivos. El servidor lee el disco y responde por RPC. Para el programador del cliente, la llamada funcionó exactamente igual que si el disco estuviera conectado localmente.

  

#### Glosario de siglas

- `RPC - Remote Procedure Call: Llamada a Procedimiento Remoto`
    
      
    
- `NFS - Network File System: Sistema de Archivos de Red`
    
      
### Tema 5: Protocolo de Transporte en Tiempo Real (RTP) y RTCP

#### Desarrollo teórico

El protocolo **RTP** (_Real-Time Transport Protocol_, RFC 3550) se sitúa conceptualmente en la capa de transporte, aunque habitualmente se implementa en la capa de aplicación o espacio de usuario. Se ejecuta sobre UDP para aprovechar su baja latencia y multiplexación de puertos, agregando la funcionalidad necesaria para gestionar flujos de medios continuos (audio y vídeo).

  

RTP asigna a cada paquete transmitido un número de secuencia creciente y una marca de tiempo (_timestamp_). El número de secuencia permite al receptor detectar paquetes perdidos o fuera de orden. La marca de tiempo indica el instante relativo en que fue muestreado el primer octeto del paquete, lo cual permite al receptor reconstruir el ritmo de reproducción original y eliminar la fluctuación del retardo (_jitter_) mediante un búfer de almacenamiento temporal (_playout buffer_). Asimismo, RTP define el campo de identificador de fuente de sincronización (SSRC - _Synchronization Source_) para diferenciar las corrientes de datos individuales dentro de una sesión de transporte compartida, y el identificador de fuente de contribución (CSRC - _Contributing Source_) cuando un mezclador combina múltiples flujos.

  

Complementariamente, el protocolo **RTCP** (_Real-Time Transport Control Protocol_) opera en paralelo a RTP (utilizando normalmente el número de puerto inmediatamente superior al de RTP). RTCP no transporta datos de medios, sino paquetes de control y realimentación periódicos entre los participantes de la sesión. RTCP cumple tres funciones primordiales:

  

1. **Realimentación de calidad de servicio**: Emite reportes de receptor (RR - _Receiver Reports_) y reportes de emisor (SR - _Sender Reports_) que incluyen estadísticas de porcentaje de paquetes perdidos, _jitter_ acumulado y retardo de ida y vuelta (RTT). Esto permite a los codificadores ajustar dinámicamente la tasa de bits o la compresión según el estado de la red.
    
      
    
2. **Identificación de la fuente**: Asigna un nombre canónico (_CNAME_) para asociar múltiples flujos de RTP pertenecientes al mismo usuario (por ejemplo, sincronizar una pista de audio y una de vídeo separadas).
    
      
    
3. **Control de escala en sesiones multipunto**: Ajusta la frecuencia de envío de paquetes RTCP en función del número total de participantes para evitar que el tráfico de control consuma más del 5% del ancho de banda de la sesión.
    
      
    

#### Ejemplo práctico

En una videoconferencia multipunto, la señal de cámara de cada participante se encapsula en paquetes RTP. La marca de tiempo en el encabezado RTP asegura que la voz y los fotogramas del rostro se reproduzcan sincronizados en la pantalla del receptor. Si la conexión de un usuario se degrada, RTCP detecta el incremento de pérdida de paquetes y envía un reporte de calidad (RR); el servidor de video reacciona reduciendo la resolución de la imagen (de 1080p a 720p) para mantener la fluidez de la transmisión.

  

#### Glosario de siglas

- `RTP - Real-Time Transport Protocol: Protocolo de Transporte en Tiempo Real`
    
      
    
- `RTCP - Real-Time Transport Control Protocol: Protocolo de Control de Transporte en Tiempo Real`
    
      
    
- `UDP - User Datagram Protocol: Protocolo de Datagramas de Usuario`
    
      
    
- `RFC - Request for Comments: Petición de Comentarios`
    
      
    
- `SSRC - Synchronization Source: Fuente de Sincronización`
    
      
    
- `CSRC - Contributing Source: Fuente de Contribución`
    
      
    
- `CNAME - Canonical Name: Nombre Canónico`
    
      
    
- `RTT - Round-Trip Time: Tiempo de Ida y Vuelta`
    
      
    

### Tema 6: Protocolo de Control de Transmisión (TCP) - Modelo de Servicio y Sockets

#### Desarrollo teórico

**TCP** (_Transmission Control Protocol_, RFC 793) es el protocolo orientado a conexión principal de la capa de transporte en la arquitectura TCP/IP. Ofrece un flujo de bytes fiable de extremo a extremo a través de una red de datagramas IP no fiable.

  

- **Propiedades del Servicio TCP**:
    
      
    1. **Orientado a conexión**: Antes de transferir datos, las dos entidades de transporte deben negociar y establecer explícitamente una conexión lógica de control mediante un intercambio de sincronización.
        
          
        
    2. **Flujo de bytes no estructurado**: La capa de aplicación entrega datos a TCP como una secuencia continua de octetos. TCP no preserva las fronteras del mensaje; agrupa libremente los bytes en segmentos según la unidad máxima de transferencia (MTU) de la red subyacente.
        
          
        
    3. **Comunicación Full-Duplex**: Los datos pueden fluir simultáneamente en ambas direcciones entre los dos puntos terminales.
        
          
        
    4. **Entrega fiable y ordenada**: Garantiza que todos los bytes entregados a la aplicación receptora estén libres de errores, sin duplicados y exactamente en el orden de envío, mediante el uso de números de secuencia, acuses de recibo acumulativos (ACK) y retransmisión por temporizador (RTO).
        
          
        
- **Concepto de Sockets y Puertos**:
    
    Una conexión TCP se identifica unívocamente mediante una tupla de 4 elementos: (Dirección IP Origen, Puerto Origen, Dirección IP Destino, Puerto Destino). El punto final de la comunicación se denomina _Socket_ (combinación de Dirección IP y número de puerto de 16 bits). Las aplicaciones interactúan con TCP utilizando las primitivas de la interfaz de Sockets de Berkeley:
    
      
    - `SOCKET`: Crea una nueva terminal de comunicación.
        
          
        
    - `BIND`: Asocia una dirección IP local y puerto a un socket.
        
          
        
    - `LISTEN`: Configura el socket para aceptar conexiones entrantes (modo pasivo).
        
          
        
    - `ACCEPT`: Bloquea al servidor hasta que llega una solicitud de conexión entrante.
        
          
        
    - `CONNECT`: Inicia activamente un establecimiento de conexión de tres vías con un servidor remoto.
        
          
        
    - `SEND` / `RECV` (o `WRITE` / `READ`): Transfiere datos sobre el socket conectado.
        
          
        
    - `CLOSE`: Termina la conexión y libera los recursos del puerto.
        
          
        

#### Ejemplo práctico

Al navegar en un sitio web seguro (`[https://www.ejemplo.com](https://www.ejemplo.com)`), la aplicación cliente abre un socket local en un puerto efímero (ej. `192.168.1.15:52341`) y ejecuta `CONNECT` hacia el servidor en el puerto 443 (`93.184.216.34:443`). La conexión es bidireccional: el navegador envía peticiones HTTP y el servidor responde con las páginas web sobre la misma tupla de socket de 4 elementos.

  

#### Glosario de siglas

- `TCP - Transmission Control Protocol: Protocolo de Control de Transmisión`
    
      
    
- `IP - Internet Protocol: Protocolo de Internet`
    
      
    
- `ACK - Acknowledgment: Acuse de Recibo`
    
      
    
- `RTO - Retransmission Timeout: Tiempo de Espera de Retransmisión`
    
      
    
- `MTU - Maximum Transmission Unit: Unidad Máxima de Transferencia`
    
      
    
- `HTTP - Hypertext Transfer Protocol: Protocolo de Transferencia de Hipertexto`
    
      
    

### Tema 7: Estructura del Segmento TCP y Campos de Cabecera

#### Desarrollo teórico

La unidad de datos del protocolo TCP se denomina **Segmento**. Consta de una cabecera de tamaño variable (20 bytes como mínimo sin opciones) seguida de la carga útil de datos de aplicación.

  

- **Campos clave de la Cabecera TCP**:
    
      
    1. **Puerto de Origen y Puerto de Destino (16 bits cada uno)**: Identifican los procesos de aplicación emisor y receptor en las respectivas máquinas terminales.
        
          
        
    2. **Número de Secuencia (32 bits)**: Indica la posición en el flujo de bytes del emisor correspondiente al primer byte de datos contenido en este segmento.
        
          
        
    3. **Número de Acuse de Recibo / ACK (32 bits)**: Utiliza confirmación acumulativa; especifica el siguiente número de byte que el emisor del ACK espera recibir.
        
          
        
    4. **Longitud de Cabecera / Offset de Datos (4 bits)**: Indica el tamaño de la cabecera TCP medido en palabras de 32 bits (mínimo 5, es decir, 20 bytes).
        
          
        
    5. **Banderas o Bits de Control (6 a 8 bits)**:
        
          
        - `SYN`: Sincroniza los números de secuencia al establecer la conexión.
            
              
            
        - `FIN`: Indica que el emisor no enviará más datos (inicia la liberación).
            
              
            
        - `RST`: Aborta o reinicia una conexión ante un error grave.
            
              
            
        - `ACK`: Indica que el campo _Número de Acuse de Recibo_ es válido.
            
              
            
        - `PSH`: Solicita a TCP que entregue inmediatamente los datos a la aplicación sin esperar a llenar el búfer.
            
              
            
        - `URG`: Señala que el segmento contiene datos urgentes.
            
              
            
    6. **Tamaño de Ventana (16 bits)**: Implementa el control de flujo por ventana deslizante. Especifica el número de bytes que el emisor del segmento está dispuesto a recibir a partir del byte indicado en el campo ACK.
        
          
        
    7. **Suma de Comprobación / Checksum (16 bits)**: Proporciona verificación de errores de extremo a extremo sobre la cabecera TCP, los datos y una pseudocabecera IP.
        
          
        
    8. **Puntero de Urgencia (16 bits)**: Desplazamiento desde el número de secuencia que indica la ubicación del último byte de datos urgentes (válido si el bit URG está activo).
        
          
        
    9. **Opciones (Longitud variable)**: Permite negociar parámetros adicionales, tales como la escala de ventana (_Window Scale_), MSS (_Maximum Segment Size_) y acuses de recibo selectivos (SACK).
        
          
        

#### Ejemplo práctico

Al descargar un archivo pesado de 1 GB, el emisor TCP divide el archivo en fragmentos de 1460 bytes (MSS estándar sobre Ethernet). En la cabecera de cada segmento, el número de secuencia se incrementa exactamente en 1460 unidades por cada paquete transmitido. Si el receptor devuelve un ACK con valor 14601, le está informando al emisor: "He recibido correctamente los primeros 14,600 bytes sin errores y ahora espero el byte 14601 en adelante".

  

#### Glosario de siglas

- `MSS - Maximum Segment Size: Tamaño Máximo de Segmento`
    
      
    
- `SACK - Selective Acknowledgment: Acuse de Recibo Selectivo`
    
      
    
- `SYN - Synchronize: Sincronización`
    
      
    
- `FIN - Finish: Finalización`
    
      
    
- `RST - Reset: Reinicio`
    
      
    
- `PSH - Push: Empuje`
    
      
    
- `URG - Urgent: Urgente`
    
      
    

### Tema 8: Gestión de Conexiones TCP (Establecimiento y Liberación)

#### Desarrollo teórico

Para establecer y terminar conexiones de manera segura a través de una red que puede desordenar o duplicar paquetes, TCP emplea algoritmos formales de negociación de estado.

  

#### 1. Establecimiento de Conexión: Apertura de 3 Vías (_Three-Way Handshake_)

El cliente y el servidor negocian los números de secuencia iniciales (ISN - _Initial Sequence Number_) mediante tres pasos:

  

1. **SYN (Cliente $\rightarrow$ Servidor)**: El cliente envía un segmento con la bandera `SYN=1`, especifica su número de secuencia inicial $x$ ($seq=x$) y opciones como el MSS. La conexión pasa a estado `SYN-SENT`.
    
      
    
2. **SYN-ACK (Servidor $\rightarrow$ Cliente)**: El servidor responde con `SYN=1` y `ACK=1`, selecciona su propio número de secuencia inicial $y$ ($seq=y$), y confirma al cliente asignando $ack=x+1$. El servidor pasa a estado `SYN-RECEIVED`.
    
      
    
3. **ACK (Cliente $\rightarrow$ Servidor)**: El cliente confirma al servidor con `ACK=1`, enviando $ack=y+1$ y $seq=x+1$. La conexión queda en estado `ESTABLISHED` en ambos extremos.
    
      
    

#### 2. Liberación de Conexión: Cierre de 4 Vías

Dado que TCP es un protocolo Full-Duplex, cada sentido de la comunicación debe cerrarse independientemente:

  

1. El emisor activo envía un segmento con `FIN=1` ($seq=u$).
    
      
    
2. El receptor responde con un `ACK=1` ($ack=u+1$). La conexión entra en estado de cierre simétrico parcial (_Half-Closed_); la otra dirección sigue abierta.
    
      
    
3. Cuando el segundo extremo termina de transmitir sus datos, envía su propio segmento `FIN=1` ($seq=v$).
    
      
    
4. El emisor inicial responde con `ACK=1` ($ack=v+1$) y entra en el estado `TIME-WAIT` (esperando $2 \times \text{MSL}$, donde MSL es la Máxima Vida útil del Segmento, típicamente 120 segundos) antes de cerrar completamente la conexión para garantizar que el último ACK llegó correctamente y evitar que segmentos huérfanos interfieran en conexiones futuras.
    
      
    

#### Ejemplo práctico

Al cerrar una pestaña del navegador, TCP ejecuta la liberación de conexión. El cliente envía `FIN`. El servidor responde `ACK` a la solicitud de cierre, pero puede terminar de enviar los últimos datos encolados antes de transmitir su propio `FIN`. Una vez que el cliente responde con el último `ACK`, entra en estado `TIME-WAIT` para garantizar que la sesión libere limpiamente el socket en la tabla del sistema operativo.

  

#### Glosario de siglas

- `ISN - Initial Sequence Number: Número de Secuencia Inicial`
    
      
    
- `MSL - Maximum Segment Lifetime: Vida Máxima de Segmento`
    
      
    

### Tema 9: Control de Congestión en TCP

#### Desarrollo teórico

El control de congestión en TCP opera de forma autónoma de extremo a extremo mediante el ajuste dinámico de una ventana de congestión ($cwnd$) gestionada internamente por el emisor, la cual limita la cantidad de bytes que pueden enviarse a la red sin haber recibido acuse de recibo. El límite efectivo de transmisión es el valor mínimo entre la ventana de recepción ($rwnd$, notificada por el receptor para control de flujo) y $cwnd$:

  

$$\text{Ventana de envío} = \min(cwnd, rwnd)$$

TCP utiliza cuatro algoritmos interconectados para regular la tasa de inyección de tráfico:

  

1. **Comienzo Lento (_Slow Start_)**:
    
      
    - Al iniciar una conexión o tras una pérdida por tiempo de espera excesivo (_timeout_), se inicializa $cwnd = 1 \text{ MSS}$.
        
          
        
    - Por cada acuse de recibo (`ACK`) válido recibido, la ventana incrementa en 1 MSS ($cwnd \leftarrow cwnd + 1 \text{ MSS}$). Esto provoca un crecimiento **exponencial** de la ventana por cada RTT transcurrido (1, 2, 4, 8, 16...).
        
          
        
    - Este crecimiento continúa hasta alcanzar el umbral de comienzo lento ($ssthresh$ - _Slow Start Threshold_).
        
          
        
2. **Evitación de Congestión (_Congestion Avoidance_)**:
    
      
    - Una vez que $cwnd \ge ssthresh$, el crecimiento cambia de exponencial a **lineal**.
        
          
        
    - Por cada RTT completo, $cwnd$ se incrementa en $1 \text{ MSS}$ (o aproximadamente $1 / cwnd$ por cada ACK individual).
        
          
        
    - El algoritmo prueba la capacidad máxima de la red de forma cautelosa.
        
          
        
3. **Retransmisión Rápida (_Fast Retransmit_)**:
    
      
    - Si un segmento se pierde pero los subsecuentes llegan al receptor, este genera acuses de recibo duplicados (_Duplicate ACKs_) indicando el último byte consecutivo recibido.
        
          
        
    - Al recibir **3 ACKs duplicados** consecutivos para el mismo segmento, el emisor asume la pérdida inmediata del segmento antes de que expire el temporizador RTO y lo retransmite de inmediato.
        
          
        
4. **Recuperación Rápida (_Fast Recovery_)**:
    
      
    - Tras detectar la pérdida mediante 3 ACKs duplicados (lo que implica que la red aún entrega paquetes), no se reinicia $cwnd = 1 \text{ MSS}$.
        
          
        
    - Se ajusta $ssthresh = cwnd / 2$ y la nueva ventana de congestión se fija en $cwnd = ssthresh + 3 \text{ MSS}$.
        
          
        
    - Se continúa en fase de evitación de congestión lineal (comportamiento AIMD - _Additive Increase Multiplicative Decrease_).
        
          
        

#### Ejemplo práctico

Durante una descarga por TCP, el emisor comienza probando la red enviando 1 paquete. Al recibir el ACK, envía 2, luego 4, 8, 16 (Comienzo Lento). Cuando llega a $ssthresh = 32$, pasa a subir de a 1 paquete por RTT (33, 34, 35 - Evitación de congestión). Si en la cifra 40 se pierde un paquete y llegan 3 ACKs duplicados, TCP retransmite el paquete perdido inmediatamente (Retransmisión Rápida) y reduce la ventana a $cwnd = 20$ (Recuperación Rápida) en lugar de volver a empezar desde 1.

  

#### Glosario de siglas

- `AIMD - Additive Increase Multiplicative Decrease: Incremento Aditivo Decremento Multiplicativo`
    
      
    
- `CWND - Congestion Window: Ventana de Congestión`
    
      
    
- `RWND - Receiver Window: Ventana de Recepción`
    
      
    
- `SSTHRESH - Slow Start Threshold: Umbral de Comienzo Lento`
    
      
    

Con esto queda completada la totalidad de los temas correspondientes a la **Diapositiva 5** (Capa de Transporte: Métricas de Kleinrock, Equidad Max-Min, UDP, RPC, RTP/RTCP, Sockets TCP, Cabeceras TCP, Gestión de Conexiones y Control de Congestión TCP).