## 1. El Protocolo IPv4 (Internet Protocol version 4 - Protocolo de Internet versión 4)

El IPv4 es el "pegamento" que mantiene unida a Internet, diseñado para proporcionar una entrega de paquetes de "mejor esfuerzo" (no garantizada) desde un origen hasta un destino.

### 1.1 Estructura de la Dirección IP

- **Longitud y Formato:** Una dirección IPv4 es un número binario de 32 bits. Para facilitar su lectura, se agrupan en cuatro octetos (8 bits cada uno) separados por puntos y expresados en formato decimal (ej. 131.108.122.204).
- **Jerarquía de la Dirección:** Cada dirección se divide en dos partes principales: el **Número de RED** (prefijo) y el **Número de HOST**.
    - La porción de red identifica el segmento específico al que pertenece la interfaz.
    - La porción de host identifica el dispositivo único dentro de esa red.
- **Interfaces, no hosts:** Es crucial entender que una dirección IP no identifica a una computadora, sino a una **interfaz de red**. Si una computadora está conectada a dos redes, debe tener dos direcciones IP.

### 1.2 Cálculo de Máscaras y Prefijos

- **Máscara de Subred:** Es un número de 32 bits que, mediante el uso de "1"s binarios, indica qué parte de la dirección IP corresponde a la red.
- **Notación CIDR (Classless Inter-Domain Routing - Enrutamiento Entre Dominios Sin Clases):** Se expresa como `x.y.z.t /n`, donde `/n` indica la cantidad de bits de red (prefijo). Por ejemplo, un prefijo `/20` corresponde a una máscara `255.255.240.0`.

---

## 2. Direcciones Especiales y Capacidad de Hosts

Existen direcciones reservadas que tienen propósitos específicos en la arquitectura de red.

### 2.1 Direcciones de Red y Broadcast

- **Dirección de RED:** Es la identificación del segmento. Se obtiene poniendo en "0" todos los bits de la parte de host ($32 - n$ bits). **No se puede asignar** a ningún host físico.
- **Dirección de Broadcast (Difusión):** Se utiliza para enviar un paquete a todos los dispositivos de la red local. Se obtiene asignando "1" a todos los bits de la parte de host. Al igual que la de red, es una dirección reservada y **no asignable** a hosts individuales.
- **Loopback (Bucle de retorno):** Las direcciones en el rango `127.xx.yy.zz` se procesan localmente para pruebas de software; los paquetes enviados aquí nunca salen al cable de red.

### 2.2 Cálculo de Capacidad

El número máximo de hosts direccionables en una subred se calcula mediante la fórmula:  
**$(2^{32-n} - 2)$**  
Se restan 2 porque la primera dirección (Red) y la última (Broadcast) están reservadas.

---

## 3. Subnetting y la Puerta de Enlace

### 3.1 División en Subredes (Subnetting)

- **Propósito:** Se realiza principalmente para reducir el tráfico de **Broadcast** (Difusión) y facilitar la gestión administrativa.
- **Visibilidad:** Internamente, una organización divide su bloque IP en trozos más pequeños, pero para el mundo exterior (Internet), la red sigue apareciendo como un solo bloque grande.

### 3.2 Puerta de Enlace Predeterminada (Default Gateway)

- **Comunicación Local:** Un host puede hablar directamente con otro si comparten el mismo ID de red.
- **Comunicación Remota:** Si el destino está fuera de la red local, el host debe enviar el paquete IP a su **Puerta de enlace predeterminada**, que es la interfaz del router (enrutador) conectada a su subred.
- **Convención:** Normalmente se le asigna la dirección IP más baja disponible en la subred (ej. la .1).

---

## 4. Protocolo NAT (Network Address Translation - Traducción de Direcciones de Red)

NAT es una técnica esencial para mitigar el agotamiento de direcciones IPv4, permitiendo que redes privadas utilicen direcciones no ruteables globalmente para acceder a Internet.

### 4.1 Direcciones Privadas (RFC 1918)

Existen tres rangos que las organizaciones pueden usar libremente de forma interna, pero que **nunca** deben aparecer en la Internet pública:

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