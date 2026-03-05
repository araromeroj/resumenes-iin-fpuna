Este capítulo presenta una introducción exhaustiva a las redes de computadoras, abarcando desde sus aplicaciones básicas hasta los modelos teóricos que rigen su funcionamiento.

### 1.1 Usos de las redes informáticas

>[!note] Red Informática
>Una **red informática** es una colección de dispositivos autónomos interconectados que pueden intercambiar información.

Tradicionalmente, la interacción se basaba en el **modelo cliente-servidor**, donde un cliente solicita datos y un **servidor** los aloja y responde. Otro modelo popular es la [[1. Introducción#Comunicación de Persona a Persona (Peer-to-Peer)|comunicación entre iguales (P2P)]], donde no hay una división fija y cada usuario puede comunicarse con cualquier otro del grupo. En el ámbito del entretenimiento, destaca la **IPTV (Televisión IP)**, que entrega contenidos mediante protocolos de Internet.
Finalmente, la [[1. Introducción#Internet de los Objetos (IoT)|revolución del IoT (Internet de los Objetos)]] está conectando a la red casi cualquier dispositivo electrónico cotidiano, desde contadores de energía hasta electrodomésticos.

### 1.2 Tipos de redes informáticas

Las redes se categorizan según su función y el servicio que prestan:

- **Redes de acceso de banda ancha:** Proporcionan conectividad doméstica a alta velocidad (habitualmente 1 Gbps) a través de cobre, cable coaxial o fibra óptica.
- **Redes de proveedores de contenidos:** Utilizan **CDN (Redes de Entrega de Contenidos)**, que son conjuntos de servidores distribuidos geográficamente para situar el contenido lo más cerca posible del usuario.
- **Redes de tránsito (Backbones):** Transportan tráfico entre redes independientes y son gestionadas por **ISPs de nivel 1**, que forman la espina dorsal de Internet.
- **Redes de empresa:** Permiten la **compartición de recursos** (datos, programas y equipos) y utilizan **VPN (Redes Privadas Virtuales)** para conectar oficinas remotas como si fueran locales.

### 1.3 Tecnología de redes, de lo local a lo global

La clasificación por escala geográfica es fundamental para entender la tecnología empleada:

- [[1. Introducción#PAN (Personal Area Network)|PAN (Red de Área Personal)]]: Dispositivos que se comunican en el rango de una persona, comúnmente usando **Bluetooth**.
- [[1. Introducción#LAN (Local Area Network)|LAN (Red de Área Local):]] Redes privadas dentro de un edificio; la tecnología más común es **Ethernet (IEEE 802.3)**, que utiliza **conmutadores (switches)** para retransmitir paquetes.
- [[1. Introducción#MAN (Metropolitan Area Network)|MAN (Red de Área Metropolitana)]]: Cubre una ciudad entera, siendo las redes de televisión por cable el ejemplo más conocido.
- [[1. Introducción#WAN (Wide Area Network)|WAN (Red de Área Extensa)]]: Abarca países o continentes; utiliza **líneas de transmisión** y **elementos de conmutación** llamados **routers**.
- [[1. Introducción#Interredes (Internetworks o Red de Redes)|Internetworks]]: Un conjunto de redes incompatibles interconectadas; el dispositivo que las une y traduce se llama **pasarela (gateway)**.

### 1.4 Ejemplos de redes

Internet es el ejemplo más destacado, evolucionando desde la **ARPANET** (basada en conmutación de paquetes) hasta la infraestructura global actual. Su arquitectura se ha "aplanado", permitiendo que los proveedores de contenidos se conecten directamente con los ISPs de acceso mediante **peering**. En las redes móviles, hemos pasado por cinco generaciones, siendo la **4G LTE** y la **5G** las actuales, basadas totalmente en **conmutación de paquetes** y en un núcleo de red llamado **EPC**. Por su parte, las redes inalámbricas **802.11 (Wi-Fi)** utilizan **puntos de acceso (AP)** para conectar clientes nómadas a la red cableada.

### 1.5 Protocolos de red

Para gestionar la complejidad, las redes se organizan en una **pila de capas**, donde cada una ofrece **servicios** a la superior ocultando su implementación.

- **Entidades pares (Peers):** Procesos en la misma capa de diferentes máquinas que se comunican mediante un **protocolo**.
- **Interfaz:** Define qué operaciones pone la capa inferior a disposición de la superior.
- **Arquitectura de red:** Es el conjunto de capas y protocolos; la lista específica de protocolos usados por un sistema es su **pila de protocolos**.
- **Encapsulamiento:** Proceso donde cada capa añade una **cabecera** (y a veces un **tráiler**) al mensaje original antes de pasarlo a la capa inferior.
- **Servicios:** Pueden ser **orientados a la conexión** (como el sistema telefónico) o **sin conexión** (como el sistema postal), con diferentes niveles de **fiabilidad** mediante **acuses de recibo (acks)**.

### 1.6 Modelos de referencia

Existen dos marcos teóricos dominantes:

1. **Modelo OSI:** Tiene **siete capas** (Aplicación, Presentación, Sesión, Transporte, Red, Enlace de datos y Física) y su mayor aporte es la distinción clara entre servicios, interfaces y protocolos.
2. **Modelo TCP/IP:** Tiene **cuatro capas** (Aplicación, Transporte, Internet y Enlace); es la base de la Internet real y utiliza el protocolo **IP** como eje central. El libro utiliza un **modelo híbrido de cinco capas** (Física, Enlace, Red, Transporte y Aplicación) que combina la utilidad teórica de OSI con la practicidad de los protocolos de TCP/IP.

### 1.7 Normalización

Los estándares son vitales para la **interoperabilidad** entre fabricantes. Las normas internacionales son gestionadas por la **ISO** y la **ITU**, mientras que los estándares de Internet se desarrollan mediante informes técnicos llamados **RFC (Request For Comments)**. El comité **IEEE 802** es fundamental para la normalización de redes LAN y PAN (Ethernet, Wi-Fi, Bluetooth).

### 1.9 Unidades métricas

En redes, se utilizan prefijos métricos (Kilo, Mega, Giga) basados en potencias de 10 para las velocidades de transmisión (ej. 1 Mbps = $10^6$ bits/seg). Sin embargo, para medir memoria o archivos, se utilizan potencias de 2 (ej. 1 KB = $2^{10}$ bytes), lo que suele generar confusión en la industria.