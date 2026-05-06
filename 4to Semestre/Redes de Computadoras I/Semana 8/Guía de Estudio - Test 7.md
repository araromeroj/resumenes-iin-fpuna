Esta guía de estudio detallada profundiza en los contenidos de la **Diapositiva 9**, integrando la información técnica de los materiales de Tanenbaum sobre las tecnologías de red inalámbrica **WiFi** (**IEEE** - _Institute of Electrical and Electronics Engineers_; Instituto de Ingenieros Eléctricos y Electrónicos **802.11**) y **Bluetooth**.

---

## 1. Redes LAN Inalámbricas: WiFi (IEEE 802.11)

WiFi es el estándar dominante para redes de área local inalámbricas (**LAN** - _Local Area Network_; Red de Área Local).

### [[Arquitectura y Componentes|A. Arquitectura y Componentes]]

- **BSS (Basic Service Set; Conjunto de Servicio Básico):** Es el bloque de construcción básico. Consiste en estaciones fijas o móviles y, opcionalmente, un **AP** (_Access Point_; Punto de Acceso).
- **Modos de Operación:**
    - **Modo Infraestructura:** Las estaciones se comunican a través de un **AP**, que suele estar conectado a una red cableada.
    - **Modo Ad hoc:** Las estaciones se comunican directamente entre sí sin necesidad de un **AP** central.
- **ESS (Extended Service Set; Conjunto de Servicio Extendido):** Unión de varios **BSS** a través de un sistema de distribución (red cableada) para formar una red inalámbrica de mayor alcance.
- **SSID (Service Set Identifier; Identificador de Conjunto de Servicio):** Nombre lógico de la red inalámbrica que permite a las estaciones asociarse al **AP** correcto.

### [[Tipos de WiFi|B. La Capa Física (PHY)]]

WiFi ha evolucionado a través de múltiples versiones que operan principalmente en las bandas **ISM** (_Industrial, Scientific, and Medical_; Industrial, Científica y Médica) de 2.4 GHz y 5 GHz:

- **802.11b:** Utiliza **DSSS** (_Direct Sequence Spread Spectrum_; Espectro Ensanchado por Secuencia Directa) y alcanza hasta 11 Mbps.
- **802.11a/g:** Introdujeron **OFDM** (_Orthogonal Frequency Division Multiplexing_; Multiplexación por División de Frecuencias Ortogonales) para alcanzar 54 Mbps.
- **802.11n (WiFi 4):** Introdujo la tecnología **MIMO** (_Multiple Input Multiple Output_; Múltiple Entrada Múltiple Salida), permitiendo hasta 600 Mbps mediante múltiples antenas.
- **802.11ac (WiFi 5):** Opera en 5 GHz, usa canales más anchos y **MU-MIMO** (_Multi-User MIMO_; MIMO de Múltiples Usuarios) para velocidades de hasta 6.93 Gbps.
- **802.11ax (WiFi 6):** Mejora la eficiencia en entornos densos mediante **OFDMA** (_Orthogonal Frequency Division Multiple Access_; Acceso Múltiple por División de Frecuencias Ortogonales).

### [[Subcapa MAC y Protocolo CSMA-CA|C. Subcapa MAC y Protocolo CSMA/CA]]

Debido a que las radios son típicamente semidúplex y no pueden detectar colisiones mientras transmiten, WiFi utiliza **CSMA/CA** (_Carrier Sense Multiple Access with Collision Avoidance_; Acceso Múltiple con Detección de Portadora y Evitación de Colisiones).

- **DCF (Distributed Coordination Function; Función de Coordinación Distribuida):** Método de acceso estándar basado en competencia.
- **Detección de Canal:**
    - **Física:** Escuchar el medio.
    - **Virtual:** Mediante el **NAV** (_Network Allocation Vector_; Vector de Asignación de Red), un temporizador que indica cuánto tiempo estará ocupado el canal según la información de las tramas previas.
- **RTS/CTS (Request to Send / Clear to Send; Solicitud de Envío / Listo para Enviar):** Mecanismo opcional para resolver el problema del **terminal oculto**, donde dos estaciones no se ven entre sí pero ambas ven al **AP**.

### D. [[Servicios y tramas usados en WiFi 802.11|Ahorro de Energía y Calidad de Servicio (QoS)]]

- **Ahorro de Energía:** Los clientes pueden entrar en modo reposo y despertarse solo para recibir **Beacons** (Balizas), tramas periódicas del **AP** que anuncian tráfico pendiente. **APSD** (_Automatic Power Save Delivery_; Entrega Automática de Ahorro de Energía) optimiza esto para aplicaciones como voz sobre IP.
- **QoS (Quality of Service; Calidad de Servicio):** Implementado en 802.11e, utiliza diferentes intervalos **IFS** (_InterFrame Spacing_; Espaciado entre Tramas) como el **AIFS** (_Arbitration Inter-Frame Space_; Espacio Inter-trama de Arbitraje) para dar prioridad al tráfico de voz o video sobre los datos comunes.

---

## 2. Redes PAN Inalámbricas: Bluetooth (IEEE 802.15.1)

Bluetooth está diseñado para redes de área personal (**PAN** - _Personal Area Network_; Red de Área Personal) de bajo costo y corto alcance (unos 10 metros).

### A. Arquitectura de Red

- **Piconet:** Consiste en un nodo **Maestro** y hasta siete nodos **Esclavos** activos. El maestro dicta el reloj y la secuencia de salto de frecuencia.
- **Scatternet:** Conjunto de piconetas interconectadas a través de un nodo que participa en más de una de ellas.

### B. Pila de Protocolos y Capa Física

- **Capa de Radio:** Opera en la banda de 2.4 GHz dividida en 79 canales. Utiliza **FHSS** (_Frequency Hopping Spread Spectrum_; Espectro Ensanchado por Salto de Frecuencia), realizando hasta 1600 saltos por segundo para evitar interferencias.
- **Banda Base (Control de Enlace):** Gestiona el tiempo ranurado (slots) de 625 microsegundos y define tramas que pueden ocupar 1, 3 o 5 ranuras.
- **L2CAP (Logical Link Control and Adaptation Protocol; Protocolo de Adaptación y Control de Enlace Lógico):** Encapsula paquetes de capas superiores, gestiona la fragmentación/reensamblado y el control de errores para enlaces de datos.

### C. Perfiles Bluetooth

A diferencia de WiFi, Bluetooth define **Perfiles**, que son pilas de protocolos específicas para aplicaciones concretas (ej. manos libres, teclados, transferencia de archivos) para garantizar la interoperabilidad total entre fabricantes.

---

## 3. Otros Temas: EPC Gen2 (RFID)

Mencionado en la agenda de la diapositiva, el estándar **EPC** (_Electronic Product Code_; Código Electrónico de Producto) **Gen2** rige los sistemas de **RFID** (_Radio Frequency Identification_; Identificación por Radiofrecuencia) para la identificación y rastreo automático de objetos mediante etiquetas inalámbricas.