## Tipos de Redes

### Acceso de Banda Ancha

Servicios de **alta velocidad** para hogares (típicamente 1 Gbps) que utilizan fibra óptica (FTTH), cable coaxial (redes de televisión por cable) o DSL, para acceso a Internet.

>[!important] Ley de Metcalfe
>El valor de la Internet es directamente proporcional al cuadrado de la cantidad de usuarios.

### Acceso móviles e inalámbricas

Permiten la conectividad para dispositivos en movimiento, como portátiles y smartphones.
- **Inalámbricas:** WiFi (IEEE 802.11). Alcance limitado, típicamente dentro de un edificio. Las velocidades varían entre 11Mbps (802.11b) hasta 7 Gbps (802.11ad).
- **Redes de Celulares:** Divididas en celdas geográficas, cada una con su estación base. Su alcance es mayor, medido en kilómetros. La tecnología 4G LTE ofrece unos 100 Mbps, mientras que la 5G promete velocidades de hasta 10 Gbps.

### Proveedoras de Contenidos

Utilizan **CDN (Redes de Entrega de Contenidos)**, que son conjuntos masivos de servidores distribuidos geográficamente para situar los datos lo más cerca posible de los usuarios.

- [I] **Datacenters:** concentran cientos de miles o millones de servidores en ubicaciones únicas (la nube) para mover cantidades masivas de datos.
- [I] **CDN (Content Delivery Networks):** Conjuntos de servidores distribuidos geográficamente para que el contenido (como YT o Netflix) esté físicamente más cerca del usuario, mejorando el rendimiento.

### De Tránsito (Backbones)

Son las redes que forman la "columna vertebral" de Internet, transportando el tráfico entre los proveedores de contenido y los proveedores de acceso (ISPs).

- **Características:** Gestionadas por **ISPs de nivel 1 (Tier-1)** como AT&T o Verizon. Interconectan routers rápidos mediante enlaces de fibra óptica de gran ancho de banda.
- **Relaciones:** El intercambio de tráfico se rige por acuerdos de negocio (**peering** o tránsito de pago) en puntos de intercambio llamados **IXP**.

### De Empresa o Corporativas

Utilizadas en campus, edificios de oficinas u organizaciones para facilitar el trabajo interno.

- **Uso:** Compartición de recursos (datos, impresoras) y comunicación interna (correo, VoIP, escritorio compartido).
- **VPN (Redes Privadas Virtuales):** Conectan oficinas remotas a través de Internet para que funcionen como una sola red lógica, eliminando la "tiranía de la geografía".

---
## Según el área de alcance

### PAN (Personal Area Network)

Es una red de uso **personal**. Conecta dispositivos en el rango de una persona (unos 10 metros), comunmente usando [[Bluetooth]].

- **Rango:** Alcance de una persona (aprox. 10m).
- **Tecnologías:** Bluetooth, [[RFID]], Zigbee.
- **Uso:** Sincronizar periféricos, transferir datos entre dispositivos de un solo usuario.

### LAN (Local Area Network)

Alcance limitado a un edificio o campus (casa, oficina). Tienen **alta velocidad de transferencia** y baja latencia. La tecnología dominante es **Ethernet conmutado**.

- **Rango:** Un edificio, oficina o casa. (10m cuarto, 100m edificio, 1km campus).
- **Características:** Alta velocidad de transferencia y baja tasa de errores.
- **Tipos:**
    - **Alámbricas:** Ethernet. Cables de cobre o [[Fibra Óptica]].
    - **Inalámbricas (WLAN):** Basadas en el estándar **IEEE 802.11 (Wi-Fi)** mediante un [[Punto de Acceso]].

>[!important] Función del AP
>- [I] **Función de un punto de acceso (AP)** en una red inalámbrica 802.11 (WiFi) es retransmitir paquetes enter los ordenadores inalámbricos y entre estos e internet

### MAN (Metropolitan Area Network)

Cubre una ciudad entera.
- **Rango:** Una ciudad completa. (10 km)
- **Ejemplos:** Redes de TV por cable, WiMAX (IEEE 802.16).

### WAN (Wide Area Network)

Se extiende sobre un país o continente. Utiliza **líneas de transmisión** y **routers** para mover paquetes. Normalmente no pertenecen a una compañía y son más lentas que las LAN's.

- **Rango:** Países (100 km) o continentes (1.000 km).
- **Componentes:**
    - **Hosts:** Máquinas de usuario (donde corren las apps).
    - **Subred de comunicación:** Líneas de transmisión y [[Enrutadores]] (routers).

>[!note] Pueden ser
> - Redes de conmutación de circuitos.
> - Redes de conmutación de paquetes.

### SAN (Storage Area Networks)

Es una red de **alta velocidad**, dedicada y separada de la LAN, que conecta servidores a cabinas de almacenamiento (discos, cintas) a nivel de bloque.
- **Uso:** Conectar servidores con dispositivos de almacenamiento.

### Interredes (Internetworks o Red de Redes)

Conjunto de redes heterogéneas independientes interconectadas mediante pasarelas o routers para formar una unidad mayor. 
- **Rango:** Planeta (10.000 km o más).

- [I] **Puertas de enlace (Gateways):** Máquinas que permiten la comunicación entre redes incompatibles.
- **Internet:** La interred global que utiliza [[redes de proveedores de servicios]] (ISP).

---
## Tipos de Enlaces

| **Tipo**          | **Descripción**                                                                       | **Ejemplo**                         |
| ----------------- | ------------------------------------------------------------------------------------- | ----------------------------------- |
| **Punto a punto** | Conectan pares individuales de máquinas.                                              | Enlaces satelitales, fibra directa. |
| **Multipunto**    | Un único canal compartido; todos reciben el paquete, pero solo el destino lo procesa. | Redes Wi-Fi, Ethernet clásico.      |
### Tipos de mensajes

- [I] **Unidifusión (Unicast):** Envío de un emisor a un único receptor específico.
- [I] **Multidifusión (Multicast):** Envío a un grupo selecto de máquinas.
- [I] **Broadcasting:** A todos los equipos.
- [I] **Anycast (IPv6):** Primer equipo de un grupo.

![[R1.Mensaje.png]]

Ver: [[Mensaje - Información a transmitirse]]

---

#### Enlaces Relacionados

- [[IP]]
- 