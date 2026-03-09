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