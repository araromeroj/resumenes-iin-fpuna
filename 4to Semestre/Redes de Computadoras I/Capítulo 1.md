#RedesTest1
Este capítulo presenta una introducción exhaustiva a las redes de computadoras, abarcando desde sus aplicaciones básicas hasta los modelos teóricos que rigen su funcionamiento.

Algunos términos a saber:
- [I] **Internet:** es una red de redes, es una interconexión entre redes.
- [I] **ISP:** Internet Red Provider (Red Proveedora de Internet).
- [I] **IP (Protocolo de Internet):** etiqueta numérica irrepetible que identifica un dispositivo conectado a una red que utiliza el protocolo IP. Existen IP públicas (IPv4) y privadas (IPv6)

### 1.1 Usos de las redes informáticas

>[!note] Red Informática
>Una red informática es una **colección de dispositivos autónomos interconectados** que pueden intercambiar información.

- **Modelo cliente-servidor:** Es la base de la mayoría d elos usos de Internet; un cliente solicita información y un servidor (proceso que aloja los datos) responde la petición.
- **Comunicación Peer-to-Peer (P2P):** En este modelo no hay una división fija entre clientes y servidores; cada individuo puede comunicarse directamente con otros miembros de un grupo informal para compartir contenidos.
- **Comercio Electrónico (e-commerce):** Incluye transacciones B2C (Empresa a consumidor), B2B (empresa a empresa), C2C (consumidor a consumidor), P2P (intercambio entre pares).
- **Entretenimiento:** Destaca la IPTV (Televisión IP), que utiliza el protocolo IP para entregar programas en lugar de señales de radio o cable tradicionales.
- **Internet de los Objetos (IoT):** Se basa en la informática ubicua, donde sensores integrados en objetos cotidianos (frigoríficos, alarmas, medidores de energía) se conectan a la red.

### 1.2 Tipos de redes informáticas

Las redes se categorizan según su función y el servicio que prestan:

- **Redes de acceso de banda ancha:** Proporcionan conectividad doméstica a alta velocidad (habitualmente 1 Gbps) a través de cobre, cable coaxial, DSL o fibra óptica.
- **Redes de proveedores de contenidos:** Utilizan **CDN (Redes de Entrega de Contenidos)**, que son conjuntos de servidores distribuidos geográficamente para situar el contenido lo más cerca posible del usuario.
- **Redes de tránsito (Backbones):** Transportan tráfico entre redes independientes y son gestionadas por **ISPs de nivel 1**, que forman la espina dorsal de Internet.
- **Redes de empresa:** Permiten la **compartición de recursos** (datos, programas y equipos) y utilizan **VPN (Redes Privadas Virtuales)** para conectar oficinas remotas como si fueran locales.

### 1.3 Tecnología de redes, de lo local a lo global

La clasificación por escala geográfica es fundamental para entender la tecnología empleada:

- **PAN (Red de Área Personal):** Dispositivos que se comunican en el rango de una persona, comúnmente usando **Bluetooth**.
- **LAN (Red de Área Local):** Redes privadas dentro de un edificio; la tecnología más común es **Ethernet (IEEE 802.3)**, que utiliza **conmutadores (switches)** para retransmitir paquetes.
- **MAN (Red de Área Metropolitana):** Cubre una ciudad entera, siendo las redes de televisión por cable el ejemplo más conocido.
- **WAN (Red de Área Extensa):** Abarca países o continentes; utiliza **líneas de transmisión** y **elementos de conmutación** llamados **routers**.
- **Internetworks**: Un conjunto de redes incompatibles interconectadas; el dispositivo que las une y traduce se llama **pasarela (gateway)**.

### 1.4 Ejemplos de redes
- **Internet:** Evolucionó de **ARPANET** (primera red de conmutación de paquetes) y **NSFNET** (primer backbone de investigación).
- **Redes Móviles:** Han pasado por cinco generaciones; desde 4G LTE, la red central se basa totalmente en paquetes (**EPC**). Un proceso crítico es el **handover** (traspaso), que ocurre cuando un usuario se mueve de una celda a otra.
- **Redes Inalámbricas (WiFi):** Basadas en el estándar **802.11**. Pueden funcionar en modo infraestructura (usando un **Punto de Acceso o AP**) o en modo **ad hoc** (comunicación directa entre dispositivos).

### 1.5 Protocolos de red

Para gestionar la complejidad, las redes se organizan en una **pila de capas**, donde cada una ofrece **servicios** a la superior ocultando su implementación.

- **Protocolo:** Es un acuerdo o conjunto de reglas sobre cómo se comunican las **entidades pares** (procesos en la misma capa) en diferentes máquinas.
- **Entidades pares (Peers):** Procesos en la misma capa de diferentes máquinas que se comunican mediante un **protocolo**.
- **Aspectos del Diseño:**
    - **Sintaxis:** Formato y longitud de los encabezados.
    - **Semántica:** Significado de los campos.
    - **Temporización:** Sincronización y timers.
- **Diseño de Capas:** Incluye mecanismos de **confiabilidad** (detección de errores), **control de flujo** (evitar saturar al receptor), **segmentación** (dividir mensajes largos) y **enrutamiento**.
- **Tipos de Servicio:** Pueden ser **orientados a la conexión** (similar al teléfono: conexión, datos, desconexión) o **sin conexión** (**datagramas**, similar al correo postal) con diferentes niveles de **fiabilidad** mediante **acuses de recibo (acks)**.
- **Servicio vs Protocolo:** El **servicio** define _qué_ hace la capa (abstracción), mientras que el **protocolo** define _cómo_ se implementa ese servicio.
- **Interfaz:** Define qué operaciones pone la capa inferior a disposición de la superior.
- **Arquitectura de red:** Es el conjunto de capas y protocolos; la lista específica de protocolos usados por un sistema es su **pila de protocolos**.
- **Encapsulamiento:** Proceso donde cada capa añade una **cabecera** (y a veces un **tráiler**) al mensaje original antes de pasarlo a la capa inferior.

### 1.6 Modelos de referencia

Existen dos marcos teóricos dominantes:

1. **Modelo OSI:** Tiene **siete capas** (Aplicación, Presentación, Sesión, Transporte, Red, Enlace de datos y Física) y su mayor aporte es la distinción clara entre servicios, interfaces y protocolos.
2. **Modelo TCP/IP:** Tiene **cuatro capas** (Aplicación, Transporte, Internet y Enlace); es la base de la Internet real y utiliza el protocolo **IP** como eje central.
3. **Modelo híbrido:** Tiene **cinco capas** (Física, Enlace, Red, Transporte y Aplicación) que combina la utilidad teórica de OSI con la practicidad de los protocolos de TCP/IP.

### 1.7 Normalización

Los estándares son vitales para la **interoperabilidad** entre fabricantes. Las normas internacionales son gestionadas por la **ISO** y la **ITU**, mientras que los estándares de Internet se desarrollan mediante informes técnicos llamados **RFC (Request For Comments)**. El comité **IEEE 802** es fundamental para la normalización de redes LAN y PAN (Ethernet, Wi-Fi, Bluetooth).
- **Estándares de facto:** Aquellos que se imponen por uso masivo sin un plan formal (ej. HTTP).
- **Estándares de jure:** Adoptados por organismos oficiales (ej. **IEEE 802** para LANs, **ISO**, **ITU**).
- **IETF (Internet Engineering Task Force):** Grupo que desarrolla estándares de Internet mediante documentos técnicos llamados **RFC (Request For Comments)**.

### 1.8 Cuestiones Sociales y Legales

- **Neutralidad de la Red:** Principio de que los ISPs deben tratar todo el tráfico de la misma forma, sin bloquear, estrangular o priorizar contenidos por pago.
- **Seguridad:** Incluye la defensa contra ataques **DDoS** (ataques masivos desde **botnets**) y el filtrado de **spam**.
### 1.9 Unidades métricas

En redes, se utilizan prefijos métricos (Kilo, Mega, Giga) basados en potencias de 10 para las velocidades de transmisión (ej. 1 Mbps = $10^6$ bits/seg). Sin embargo, para medir memoria o archivos, se utilizan potencias de 2 (ej. 1 KB = $2^{10}$ bytes), lo que suele generar confusión en la industria.

- **Tasas de bits:** Se usan prefijos métricos en **potencias de 10** (103,106). Ej: 1 Mbps = 1,000,000 bits/seg.
- **Almacenamiento/Memoria:** Se usan **potencias de 2** (210,220). Ej: 1 KB = 1024 bytes.
- **Nomenclatura:** Se usa "**b**" minúscula para bits y "**B**" mayúscula para bytes (unidades de 8 bits).

---


# Enlaces relacionados

- [[Usos de las Redes]]
- [[Arquitectura y Clasificación de Redes]]
- [[Modelo OSI]]
- [[Modelo TCP-IP]]
