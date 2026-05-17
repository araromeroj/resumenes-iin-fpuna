## 1. El Protocolo IPv4 (Internet Protocol version 4 - Protocolo de Internet versión 4)

El protocolo IPv4 es el pilar de la capa de red en la Internet moderna. Proporciona un servicio de entrega de datagramas (mensajes de capa de red) de "mejor esfuerzo", lo que significa que no garantiza la llegada, pero hace lo posible por enrutar el paquete hacia su destino.

### 1.1 Estructura y Longitud

- **Definición y Longitud:** Una dirección IPv4 es una dirección lógica de 32 bits que define de forma única la conexión de un dispositivo (ya sea un host, un servidor o un router -enrutador-) a una red IP (Internet Protocol - Protocolo de Internet).
- **Notación y Formato:** Para que sea legible por humanos, los 32 bits se agrupan en cuatro octetos (8 bits cada uno). Se utiliza la **Notación Decimal con Puntos**, donde cada octeto se convierte a un número decimal entre 0 y 255 (ej. 128.11.3.31).
- **Jerarquía de la Dirección:** Toda dirección IP se divide en dos partes:
    1. **Número de RED (Prefijo):** Identifica el segmento de red específico.
    2. **Número de HOST:** Identifica el dispositivo único dentro de esa red.
- **Gestión Global:** Las direcciones son asignadas globalmente por la **ICANN** (Internet Corporation for Assigned Names and Numbers - Corporación de Internet para la Asignación de Nombres y Números) a través de registros regionales como **LACNIC** (Latin American and Caribbean Internet Addresses Registry - Registro de Direcciones de Internet para América Latina y el Caribe).
- **Interfaces, no hosts:** Es crucial entender que una dirección IP no identifica a una computadora, sino a una **interfaz de red**. Si una computadora está conectada a dos redes, debe tener dos direcciones IP.

![[Pasted image 20260514110149.png|500]]
#### Campos de la Cabecera IPv4:

*   **Versión (4 bits):** Indica la versión del protocolo (actualmente 4).
*   **IHL (Internet Header Length; Longitud de la Cabecera de Internet):** Indica cuántas palabras de 32 bits tiene la cabecera (mínimo 5).
*   **Servicios Diferenciados:** Utilizado para indicar la prioridad del paquete.
*   **Longitud Total:** Tamaño completo del datagrama (cabecera + datos).
*   **Identificación, Flags (DF/MF) y Fragment Offset:** Campos utilizados para la fragmentación y reensamblado de paquetes cuando estos superan el **MTU** (**Maximum Transmission Unit**; Unidad Máxima de Transmisión) de un enlace.
*   **TTL (Time to Live; Tiempo de Vida):** Contador que disminuye en cada salto de router para evitar que los paquetes circulen infinitamente en bucles 
*   **Protocolo:** Indica qué protocolo de transporte sigue (ej. **TCP** o **UDP**).
*   **Checksum de Cabecera:** Suma de comprobación para detectar errores solo en la cabecera.
*   **Direcciones de Origen y Destino:** Direcciones lógicas de 32 bits de los hosts.

![[Pasted image 20260513182752.png]]

### 1.2 Cálculo de Máscaras, Prefijos y Capacidad de Hosts

- **Máscara de Subred:** Es un valor de 32 bits que utiliza "1"s binarios para indicar la porción de red y "0"s para la porción de host. Al realizar una operación lógica **AND** (Y) entre la IP y la máscara, el router obtiene la dirección de red.
- **Prefijo (Notación CIDR - Classless Inter-Domain Routing - Enrutamiento Entre Dominios Sin Clases):** Se expresa como `/n`, donde `n` es el número de bits de la red. Por ejemplo, una máscara `255.255.240.0` corresponde a un prefijo `/20`.
- **Agregación de Rutas:** Esta técnica permite juntar múltiples prefijos IP en una sola entrada más grande en la tabla de enrutamiento, reduciendo su tamaño y mejorando la eficiencia de los routers centrales.

![[Pasted image 20260514110341.png]]

- **Cálculo de Capacidad:** El número máximo de dispositivos direccionables en una subred se calcula con la fórmula ($2^{32−n}−2$, siendo $n$ la cantidad de bits de la red). Se restan dos direcciones porque:
	- La **Dirección de RED** (todos los bits de host en 0) está reservada para identificar al segmento.
	- La **Dirección de Broadcast (Difusión)** (todos los bits de host en 1) está reservada para enviar datos a todos los hosts de la subred y no puede asignarse individualmente.

---

## 2. Direcciones Especiales

Existen direcciones reservadas que tienen propósitos específicos en la arquitectura de red.

### 2.1 Direcciones de Red y Broadcast

- **Dirección de RED:** Es la identificación del segmento. Se obtiene poniendo en "0" todos los bits de la parte de host ($32 - n$ bits). **No se puede asignar** a ningún host físico. Los hosts solo pueden comunicarse con los hosts que tienen el mismo ID de red.
- **Esta red:** todos los campos rellenos de "0"
- **Un host en esta red:** 00 ... 00 | Host. Todos son "0" al inicio en la parte de RED.
- **Dirección de Broadcast (Difusión):** Se utiliza para enviar un paquete a todos los dispositivos de la red local. Se obtiene asignando "1" a todos los bits de la parte de host. Al igual que la de red, es una dirección reservada y **no asignable** a hosts individuales. El máximo de hosts en un bloque es igual a ($2^{32-n}-2$).
	- **Difusión en red local:** Todo "1" en el campo de host y en el campo de red.
	- **Difusión en red distante:** Red | 111 ... 111. Todo "1" en el campo de host.
- **Loopback (Bucle de retorno):** Las direcciones en el rango `127.xx.yy.zz` se procesan localmente para pruebas de software; los paquetes enviados aquí nunca salen al cable de red.

![[Pasted image 20260514110515.png]]


---

## 3. Subnetting y la Puerta de Enlace

### 3.1 División en Subredes (Subnetting)

- **Propósito:** Se realiza principalmente para reducir el tráfico de **Broadcast** (Difusión) y facilitar la gestión administrativa.
- **Visibilidad:** Internamente, una organización divide su bloque IP en trozos más pequeños, pero para el mundo exterior (Internet), la red sigue apareciendo como un solo bloque grande.
- **Prefijo más largo coincidente:** Los paquetes son enviados a la entrada con el prefijo más largo coincidente o bloque de direcciones más pequeño. Complica el envío pero agrega flexibilidad.

![[Pasted image 20260514111228.png]]
### 3.2 Puerta de Enlace Predeterminada (Default Gateway)

- **Comunicación Local:** Un host puede hablar directamente con otro si comparten el mismo ID de red.
- **Comunicación Remota:** Si el destino está fuera de la red local, el host debe enviar el paquete IP a su **Puerta de enlace predeterminada**, que es la interfaz del router (enrutador) conectada a su subred.
- **Convención:** Normalmente se le asigna la dirección IP más baja disponible en la subred (ej. la .1).

---

## 4. Protocolo NAT (Network Address Translation - Traducción de Direcciones de Red)

NAT es una técnica esencial para mitigar el agotamiento de direcciones IPv4, permitiendo que redes privadas utilicen direcciones no ruteables globalmente para acceder a Internet.
- Consiste en el cambio de direcciones IP y/o los puertos de origen/destino de paquetes entrantes y salientes.
- Se puede usar direcciones privadas LANs internas y tener una sola dirección IP global a Internet.
- **Objetivo:** paliar la escasez de direcciones IP v4
### 4.1 Direcciones Privadas (RFC 1918)

Existen tres rangos que las organizaciones pueden usar libremente de forma interna, pero que **nunca** deben aparecer en la Internet pública:

>[!tip] Importante
>Pueden ser usadas por:
>- Las subredes que usan NAT, para conectarse a Internet.
>- Los hosts que no se conectan a Internet.

- `10.0.0.0` a `10.255.255.255` (Clase A).
- `172.16.0.0` a `172.31.255.255` (Clase B).
- `192.168.0.0` a `192.168.255.255` (Clase C).

### 4.2 Tipos de NAT

1. **NAT Estática:** Mapeo permanente uno a uno entre una IP privada y una pública.
2. **NAT Dinámica:** El router tiene un grupo (_pool_) de direcciones públicas y asigna una temporalmente a un host interno solo cuando este requiere conexión a Internet.
3. **PAT (Port Address Translation - Traducción de Direcciones de Puerto):** También llamada **NAT con sobrecarga**. Es la más común (usada en hogares). Permite que cientos de dispositivos usen una **única IP pública** diferenciando las conexiones mediante los números de puerto TCP (Transmission Control Protocol - Protocolo de Control de Transmisión) y UDP (User Datagram Protocol - Protocolo de Datagramas de Usuario).

### 4.3 Objeciones Técnicas a NAT

Tanenbaum señala que NAT es criticado por:

- Violar la independencia de las capas (la capa de red asume datos de transporte).
- Convertir una red "sin conexión" en una "orientada a la conexión" al forzar al router a mantener el estado de cada sesión.
- Dificultar aplicaciones como FTP (File Transfer Protocol - Protocolo de Transferencia de Archivos) que insertan direcciones IP dentro de los datos del mensaje.

---

## 5. Routers: Estructura y Funcionamiento

### 5.1 Función y Estructura

La misión principal de un router es retransmitir paquetes entre sus interfaces basándose en la información de Capa 3. Internamente, un router es similar a una computadora personal con CPU (Central Processing Unit - Unidad Central de Procesamiento), memoria y un sistema operativo, frecuentemente el **IOS** (Internetwork Operating System - Sistema Operativo de Interconexión de Redes).

### 5.2 Memoria del Router

- **RAM (Random Access Memory - Memoria de Acceso Aleatorio):** Almacena la tabla de enrutamiento y la configuración en ejecución (_running configuration_).
- **NVRAM (Non-Volatile RAM - RAM No Volátil):** Guarda la configuración de inicio (_start-up configuration_) que se carga al encender el equipo.
- **Flash:** Almacena la imagen del sistema operativo.

### 5.3 Tabla de Enrutamiento

Contiene las rutas hacia los destinos conocidos:

- **Rutas Directas:** Se agregan automáticamente cuando una interfaz está activa.
- **Rutas Estáticas:** Configuradas manualmente por el administrador.
- **Rutas Dinámicas:** Aprendidas mediante protocolos de enrutamiento como **RIP** (Routing Information Protocol - Protocolo de Información de Enrutamiento), **OSPF** (Open Shortest Path First - Abrir el Camino Más Corto Primero) y **BGP** (Border Gateway Protocol - Protocolo de Gateway de Frontera).

---

## 6. Protocolos de Soporte: ARP, ICMP y DHCP

### 6.1 ARP (Address Resolution Protocol - Protocolo de Resolución de Direcciones)

- **Función:** Mapea una dirección lógica (IP) a una dirección física (MAC - Media Access Control).
- **Mecanismo:** Un host envía una solicitud por **broadcast** preguntando "¿Quién tiene esta IP?"; el dueño responde con su dirección MAC de 48 bits.
- **Proxy ARP:** Caso donde el router responde con su propia MAC en nombre de un host que está en otra red.

### 6.2 ICMP (Internet Control Message Protocol - Protocolo de Mensajes de Control de Internet)

Se utiliza para reportar errores y diagnosticar problemas de red.

- **Ping:** Usa mensajes _Echo Request_ y _Echo Reply_ para verificar conectividad.
- **Tracert / Traceroute:** Herramienta que muestra todos los saltos (routers) por los que pasa un paquete, manipulando el campo TTL (Time To Live - Tiempo de Vida) de la cabecera IP.

### 6.3 DHCP (Dynamic Host Configuration Protocol - Protocolo de Configuración Dinámica de Host)

Permite que un dispositivo obtenga automáticamente su dirección IP, máscara y puerta de enlace al conectarse a la red. Funciona mediante un proceso de **arrendamiento** (_lease_) donde la IP se asigna por un tiempo limitado.