Esta guía de estudio detalla profundamente los conceptos de la **Diapositiva 11**, centrada en la **Capa de Red** y el protocolo **IP** (**Internet Protocol**; Protocolo de Internet), complementada con la información técnica del libro de Tanenbaum.

---

## 1. La Capa de Red en Internet

La capa de red es la encargada de transportar paquetes desde el host de origen hasta el de destino, lo que puede requerir atravesar múltiples **routers** (enrutadores) intermedios. Es la capa más baja que se ocupa de la comunicación de extremo a extremo.

*   **La Internet como Interconexión:** Se define como una colección vasta de redes o **AS** (**Autonomous Systems**; Sistemas Autónomos) interconectados. No tiene una estructura centralizada, pero se organiza jerárquicamente con redes de Nivel 1 (backbones), **ISP** (**Internet Service Providers**; Proveedores de Servicios de Internet) regionales y redes periféricas (universidades, empresas).
*   **Principios de Diseño (RFC 1958):** El éxito de **IP** (**Internet Protocol**; Protocolo de Internet) se basa en principios como "asegurar que funcione", "mantenerlo simple" y el "principio de extremo a extremo" (la inteligencia debe estar en los hosts, no en la red).

---

## 2. El Protocolo IPv4 (Internet Protocol version 4)

Un datagrama **IPv4** (**Internet Protocol version 4**; Protocolo de Internet versión 4) consta de una cabecera fija de 20 bytes y una parte opcional.

#### **Campos de la Cabecera IPv4:**
*   **Versión (4 bits):** Indica la versión del protocolo (actualmente 4).
*   **IHL (Internet Header Length; Longitud de la Cabecera de Internet):** Indica cuántas palabras de 32 bits tiene la cabecera (mínimo 5).
*   **Servicios Diferenciados:** Utilizado para indicar la prioridad del paquete.
*   **Longitud Total:** Tamaño completo del datagrama (cabecera + datos).
*   **Identificación, Flags (DF/MF) y Fragment Offset:** Campos utilizados para la fragmentación y reensamblado de paquetes cuando estos superan el **MTU** (**Maximum Transmission Unit**; Unidad Máxima de Transmisión) de un enlace.
*   **TTL (Time to Live; Tiempo de Vida):** Contador que disminuye en cada salto de router para evitar que los paquetes circulen infinitamente en bucles 
*   **Protocolo:** Indica qué protocolo de transporte sigue (ej. **TCP** o **UDP**).
*   **Checksum de Cabecera:** Suma de comprobación para detectar errores solo en la cabecera.
*   **Direcciones de Origen y Destino:** Direcciones lógicas de 32 bits de los hosts.

---

## 3. Direccionamiento IPv4

Una dirección **IPv4** (**Internet Protocol version 4**; Protocolo de Internet versión 4) es un identificador lógico único y universal de 32 bits que define la conexión de un dispositivo a la red.

*   **Representación:** Se agrupan en 4 octetos (8 bits cada uno) separados por puntos y se expresan en decimal (ej. `128.11.3.31`).
*   **Jerarquía de la Dirección:** Toda dirección se compone de dos partes principales:
    1.  **Número de Red:** Identifica la red a la que pertenece el host.
    2.  **Número de Host:** Identifica de forma única al dispositivo dentro de esa red.
*   **Gestión Global:** El **ICANN** (**Internet Corporation for Assigned Names and Numbers**; Corporación de Internet para la Asignación de Nombres y Números) asigna bloques de direcciones a los **ISP** (**Internet Service Providers**; Proveedores de Servicios de Internet).

---

## 4. Prefijos, Máscaras y CIDR

Para gestionar el agotamiento de direcciones, se pasó del direccionamiento por clases (A, B, C) al sistema **CIDR** (**Classless Inter-Domain Routing**; Enrutamiento Interdominio sin Clases).

*   **Máscara de Subred:** Es un número de 32 bits (usualmente con 1s seguidos de 0s) que ayuda al router a determinar qué parte de la dirección es red y qué parte es host.
*   **Notación de Prefijo (/n):** Define la longitud de la máscara. Por ejemplo, `/20` equivale a una máscara `255.255.240.0`.
*   **Bloques de Direcciones:** Se definen como `x.y.z.t/n`, donde la primera parte es una dirección del bloque y `/n` indica cuántos bits son fijos para la red.

---

## 5. Subnetting (División en Subredes)

El **Subnetting** (subredes) permite a una organización dividir internamente un bloque de direcciones grande en redes más pequeñas y manejables.

*   **Funcionamiento:** Se "toman prestados" bits de la parte de host para crear identificadores de subred.
*   **Uso en Routers:** Cuando un paquete llega al router principal, este utiliza la máscara de subred para saber a qué red local específica debe reenviar el tráfico.

---

## 6. Direcciones IPv4 Especiales

Existen rangos con funciones predefinidas que no se pueden asignar a hosts normales en la Internet pública:
*   **0.0.0.0:** Se refiere a "este host".
*   **127.x.x.x:** Direcciones de **Loopback** (retorno); se usan para que un host se envíe paquetes a sí mismo para pruebas.
*   **Difusión (Broadcast):** Direcciones con todos los bits de host en 1 (ej. `255.255.255.255` para la red local).
*   **IPs Privadas:** Rangos reservados (como `10.x.x.x`) para uso interno que no pueden aparecer en la Internet pública sin traducción.

---

## 7. Protocolos de Apoyo y NAT

Debido a que **IP** (**Internet Protocol**; Protocolo de Internet) es un protocolo de "mejor esfuerzo" y las direcciones son escasas, se requieren mecanismos adicionales:

*   **ICMP (Internet Control Message Protocol; Protocolo de Mensajes de Control de Internet):** Utilizado por los routers y hosts para reportar errores en la entrega de paquetes o realizar diagnósticos (como el comando `ping`).
*   **ARP (Address Resolution Protocol; Protocolo de Resolución de Direcciones):** Permite obtener la dirección física (**MAC**; **Medium Access Control**; Control de Acceso al Medio) de un dispositivo cuando solo se conoce su dirección **IP**.
*   **NAT (Network Address Translation; Traducción de Direcciones de Red):** Permite que múltiples dispositivos en una red privada compartan una única dirección **IP** pública para acceder a Internet, traduciendo las direcciones y puertos en el router de salida.