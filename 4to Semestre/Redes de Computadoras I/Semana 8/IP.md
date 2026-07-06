**IP (Protocolo de Internet)** es una etiqueta numérica única e irrepetible que identifica a cualquier dispositivo, conectado a una red que utiliza el protocolo IP.

>[!important] Formato
>XXX.XXX.XXX.XXX
>Cada "XXX" tiene un rango de valor de 0 a 255

> **Un poco de historia**
> Anteriormente se daban IP's a cada empresa dentro de un rango dado, se registraban en papeles nada más para llevar cuenta de las IP's disponibles y las dadas.


**Registros Regionales de Internet (RIR):**

- ARIN: Norteamérica, EEUU, Canadá.
- RIPE, NIC: Europa, Medio Oriente y Asia Central.
- APNIC: Asia y Costa del Pacífico.
- LACNIC: Latinoamérica.
- AFRINIC: Continente africano

---
## Clasificación
### Según la versión
#### IPv4 (Protocolo de Internet Versión 4)

La que domina Internet actualmente.

>[!Important] Características
> - Utiliza direcciones de 32 bits, lo que permite aproximadamente 4 mil millones de direcciones únicas.
> - Su cabecera tiene una parte fija de **20 bytes** y 13 campos para fragmentación y una suma de comprobación (checksum).
> - Debido a su popularidad, las direcciones se han agotado, lo que llevó al uso de técnicas temporales como NAT y la creación del IPv6


| **Campo**                                            | **Tamaño** | **Función Principal**                                  |
| ---------------------------------------------------- | ---------- | ------------------------------------------------------ |
| **Versión**                                          | 4 bits     | Indica la versión de IP (4).                           |
| **IHL(Internet Header Length)**                      | 4 bits     | Longitud del encabezado (en palabras de 32 bits).      |
| **Longitud Total**                                   | 16 bits    | Tamaño total del paquete (encabezado + datos).         |
| **Tipo de Servicio (ToS o Differentiated Services)** | 8 bits     | Prioridad y calidad de servicio (QoS).                 |
| **Identificación**                                   | 16 bits    | Identificador único para reensamblar fragmentos.       |
| **Banderas (Flags)**                                 | 3 bits     | Control de fragmentación (DF, MF).                     |
| **Offset de Fragmento**                              | 13 bits    | Posición de este fragmento en el paquete original.     |
| **Tiempo de Vida (TTL)**                             | 8 bits     | Evita bucles infinitos (límite de saltos por routers). |
| **Protocolo**                                        | 8 bits     | Indica el protocolo de capa superior (ej. TCP, UDP).   |
| **Checksum del Encabezado**                          | 16 bits    | Verificación de errores solo para el encabezado.       |
| **IP Origen**                                        | 32 bits    | Dirección IP del remitente.                            |
| **IP Destino**                                       | 32 bits    | Dirección IP del destinatario.                         |
| **Opciones**                                         | Variable   | (Opcional) Funciones de red especiales/depuración.     |
| **Relleno (Padding)**                                | Variable   | Asegura que el encabezado sea múltiplo de 32 bits.     |

>[!info]- Descripción detallada de los campos
> Descripción Detallada de los Campos
> 
> 1. Versión (Version)
>     
>     Tamaño: 4 bits.
>     
>     Descripción: Indica la versión del protocolo de Internet que se está utilizando. Para IPv4, este valor siempre es 4 (en binario 0100). Permite a los routers saber cómo leer el resto del encabezado.
>     
> 2. Longitud del Encabezado (IHL - Internet Header Length)
>     
>     Tamaño: 4 bits.
>     
>     Descripción: Especifica la longitud total del encabezado IPv4 en palabras de 32 bits. Como el tamaño mínimo del encabezado es de 20 bytes, el valor mínimo normal de este campo es 5 (5 palabras x 4 bytes = 20 bytes).
>     
> 3. Tipo de Servicio (ToS - Type of Service / Differentiated Services)
>     
>     Tamaño: 8 bits.
>     
>     Descripción: Utilizado para especificar cómo debe ser manejado el paquete por los routers (Calidad de Servicio o QoS). Permite priorizar ciertos tipos de tráfico, como voz sobre IP (VoIP) o transmisión de video, por encima de tráfico menos urgente.
>     
> 4. Longitud Total (Total Length)
>     
>     Tamaño: 16 bits.
>     
>     Descripción: Define el tamaño total de todo el paquete IPv4, incluyendo tanto el encabezado como los datos (payload). Se mide en bytes. El tamaño máximo posible es de 65,535 bytes.
>     
> 5. Identificación (Identification)
>     
>     Tamaño: 16 bits.
>     
>     Descripción: Cuando un paquete es demasiado grande para la red y debe ser dividido (fragmentado), a todos los fragmentos resultantes se les asigna el mismo número de identificación para que el receptor original sepa a qué paquete pertenecen y pueda reensamblarlos.
>     
> 6. Banderas (Flags)
>     
>     Tamaño: 3 bits.
>     
>     Descripción: Controlan y gestionan la fragmentación del paquete.
>     
>     Bit 0: Reservado (siempre es 0).
>     
>     Bit 1 (DF - Don't Fragment): Si es 1, le dice a los routers que no pueden fragmentar el paquete. Si el paquete es demasiado grande, se descarta.
>     
>     Bit 2 (MF - More Fragments): Si es 1, indica que este no es el último fragmento del paquete original. El último fragmento tiene este bit en 0.
>     
> 7. Desplazamiento del Fragmento (Fragment Offset)
>     
>     Tamaño: 13 bits.
>     
>     Descripción: Si un paquete ha sido fragmentado, este campo indica la posición exacta de los datos de este fragmento en relación con el inicio de los datos del paquete original, permitiendo el reensamblaje en el orden correcto.
>     
> 8. Tiempo de Vida (TTL - Time To Live)
>     
>     Tamaño: 8 bits.
>     
>     Descripción: Evita que los paquetes se queden atrapados en bucles infinitos de enrutamiento. Representa el número máximo de "saltos" (routers) que el paquete puede atravesar. Cada vez que pasa por un router, el TTL disminuye en 1. Si llega a 0, el paquete se descarta y se envía un mensaje de error ICMP al origen.
>     
> 9. Protocolo (Protocol)
>     
>     Tamaño: 8 bits.
>     
>     Descripción: Indica qué protocolo de la capa de transporte (Capa 4 del modelo OSI) está encapsulado en los datos del paquete IP. Ejemplos comunes:
>     
>     1 = ICMP (Ping)
>     
>     6 = TCP
>     
>     17 = UDP
>     
> 10. Suma de Comprobación del Encabezado (Header Checksum)
>     
>     Tamaño: 16 bits.
>     
>     Descripción: Un cálculo matemático utilizado para detectar errores o corrupción solo en el encabezado IPv4 durante la transmisión. Los routers lo recalculan en cada salto porque campos como el TTL cambian constantemente.
>     
> 11. Dirección IP de Origen (Source IP Address)
>     
>     Tamaño: 32 bits.
>     
>     Descripción: La dirección IPv4 lógica de la máquina o dispositivo que está enviando el paquete.
>     
> 12. Dirección IP de Destino (Destination IP Address)
>     
>     Tamaño: 32 bits.
>     
>     Descripción: La dirección IPv4 lógica de la máquina o dispositivo al que va dirigido el paquete.
>     
> 13. Opciones (Options)
>     
>     Tamaño: Variable (0 a 40 bytes).
>     
>     Descripción: Es un campo raramente utilizado en la actualidad. Estaba pensado para fines de pruebas de red, depuración y características especiales de enrutamiento estricto.
>     
> 14. Relleno (Padding)
>     
>     Tamaño: Variable.
>     
>     Descripción: Si el campo de "Opciones" se utiliza y no termina en un límite de 32 bits, se añaden ceros adicionales (relleno) para asegurar que el encabezado total termine en un múltiplo de 32 bits, lo cual es requerido por el campo IHL.
>

---


#### IPv6 (Protocolo de Internet Versión 6)


>[!important] Características
> - Utiliza direcciones de 128 bits, proporcionando un espacio virtualmente ilimitado (aproximadamente $3*10^38$ direcciones).
> - La cabecera se simplificó a 7 campos (frente a los 13 de IPv4) para que los enrutadores procesen los paquetes más rápido.
> - No tienen suma de comprobación en la cabecera para mejorar el rendimiento.
> - La fragmentación solo la realiza el host de origen, no los enrutadores intermedios, lo que agiliza el tráfico.

### Según su Uso y Estructura

- **Direcciones Públicas vs. Privadas:** Las direcciones privadas se usan internamente en redes domésticas o de empresas y no pueden aparecer en el Internet global. Los rangos reservados son **10.0.0.0/8**, **172.16.0.0/12** y **192.168.0.0/16**.
- **Direccionamiento con Clases (Classful):** Diseño antiguo que dividía las direcciones en clases fijas (**A, B, C, D y E**) según sus bits iniciales. Fue reemplazado por CIDR porque desperdiciaba muchas direcciones.
- **CIDR (Enrutamiento entre Dominios sin Clases):** Permite que los bloques de direcciones tengan **tamaños variables** mediante el uso de máscaras de subred, facilitando la agregación de rutas y reduciendo el tamaño de las tablas de enrutamiento.
- **Direcciones Especiales:**
    - **0.0.0.0:** Utilizada por los hosts al arrancar ("esta red").
    - **Loopback (127.xx.yy.zz):** Paquetes que no salen al cable y se procesan localmente para pruebas.

---
## Videos y Enlaces Relacionados

- Qué es la IP privada, NAT y puerta de enlace:
	https://www.youtube.com/watch?v=HeZWcZmrQUY
- Arquitectura y Clasificación del Protocolo de Internet:
	https://notebooklm.google.com/notebook/0f78dd09-cd89-4f4d-b999-e6202ee28b88