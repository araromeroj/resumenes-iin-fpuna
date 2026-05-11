Esta guía de estudio detalla los contenidos fundamentales presentados en la **Diapositiva 11**, la cual aborda el **Capítulo 5: La Capa de Red**, centrándose en el protocolo **IP (Internet Protocol - Protocolo de Internet)** y sus mecanismos de apoyo.

---

## 1. El Protocolo IP (Internet Protocol - Protocolo de Internet)

La capa de red es la responsable de transportar paquetes desde el host de origen hasta el host de destino, realizando múltiples saltos a través de **routers (enrutadores)** intermedios si es necesario. Es la capa más baja que se ocupa de la comunicación de extremo a extremo.

*   **Naturaleza del servicio:** El protocolo **IP (Internet Protocol - Protocolo de Internet)** proporciona un servicio de datagramas no orientado a la conexión.
*   **Funcionamiento:** Permite a los hosts inyectar paquetes en la red, los cuales viajan de forma independiente a través de las subredes hasta alcanzar su destino. No garantiza que los paquetes lleguen en orden ni que lleguen en absoluto (entrega de "mejor esfuerzo").

---

## 2. Direccionamiento IPv4 (Internet Protocol version 4 - Protocolo de Internet versión 4)

El direccionamiento es el mecanismo que identifica de forma lógica a cada dispositivo en la red global.

*   **Direccionamiento por clases:** Antes de 1993, las direcciones se dividían rígidamente en clases:
    *   **Clase A:** Para redes masivas con hasta 16 millones de hosts.
    *   **Clase B:** Para redes medianas (hasta 65,536 hosts).
    *   **Clase C:** Para redes pequeñas o **LAN (Local Area Network - Red de Área Local)** con hasta 256 hosts.
    *   **Clase D:** Reservada para el tráfico de **Multicast (Multidifusión)**.
    *   **Clase E:** Reservada para uso futuro.
*   **CIDR (Classless Inter-Domain Routing - Enrutamiento Interdominio sin Clases):** Es el estándar actual que reemplazó a las clases para gestionar de forma eficiente el agotamiento de direcciones **IPv4 (Internet Protocol version 4 - Protocolo de Internet versión 4)**. Permite asignar bloques de direcciones de tamaño variable, reduciendo además el tamaño de las tablas de enrutamiento global.

---

## 3. Subnetting (Subredes) y Configuración de Routers

El **Subnetting (Subredes)** es la técnica de dividir un bloque de red grande en segmentos más pequeños y manejables.

*   **Implementación:** Se utiliza para alinear la estructura lógica de la red con la estructura física o departamental de una organización.
*   **Máscaras de subred:** Son fundamentales en la configuración de los **routers (enrutadores)** para determinar a qué subred específica pertenece una dirección de destino y por qué interfaz de salida debe enviarse el paquete.

---

## 4. Protocolo NAT (Network Address Translation - Traducción de Direcciones de Red)

El protocolo **NAT (Network Address Translation - Traducción de Direcciones de Red)** surgió como una solución temporal y masiva ante la falta de direcciones públicas.

*   **Función:** Permite que una red privada utilice direcciones internas (no válidas en la Internet pública) y que todos sus dispositivos compartan una única dirección **IP (Internet Protocol - Protocolo de Internet)** pública para salir al exterior.
*   **Mecanismo:** El router traduce la dirección de origen del paquete privado a la dirección pública antes de enviarlo a la red externa.

---

## 5. Protocolo ICMP (Internet Control Message Protocol - Protocolo de Mensajes de Control de Internet)

**IP (Internet Protocol - Protocolo de Internet)** por sí solo no tiene mecanismos para reportar errores o situaciones anómalas. Para ello utiliza al protocolo **ICMP (Internet Control Message Protocol - Protocolo de Mensajes de Control de Internet)**.

*   **Propósito:** Notificar problemas en la entrega de paquetes (como host inalcanzable o tiempo de vida excedido) y realizar diagnósticos de red.
*   **Ejemplos:** El comando `ping` utiliza mensajes **ICMP (Internet Control Message Protocol - Protocolo de Mensajes de Control de Internet)** para verificar la conectividad con otro host.

---

## 6. Protocolo ARP (Address Resolution Protocol - Protocolo de Resolución de Direcciones)

Cuando un paquete llega a la **LAN (Local Area Network - Red de Área Local)** de destino, la capa de red conoce la dirección **IP (Internet Protocol - Protocolo de Internet)**, pero para transmitir la trama físicamente necesita la dirección física del hardware.

*   **Función:** Traducir o mapear direcciones lógicas **IP (Internet Protocol - Protocolo de Internet)** a direcciones físicas **MAC (Medium Access Control - Control de Acceso al Medio)**.
*   **Operación:** El dispositivo emisor envía una consulta de difusión preguntando quién tiene la **IP (Internet Protocol - Protocolo de Internet)** buscada; el dueño de dicha dirección responde enviando su dirección **MAC (Medium Access Control - Control de Acceso al Medio)**.