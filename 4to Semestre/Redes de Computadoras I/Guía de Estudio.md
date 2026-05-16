Esta guía de estudio pormenorizada abarca los contenidos fundamentales presentados desde la **Diapositiva 1** hasta la **Diapositiva 11**, integrando conceptos del material de apoyo del libro de Tanenbaum para proporcionar una comprensión profunda de las redes de computadoras.

---

## [[Diapositiva 1 - Guía de estudio|1. Introducción y Logística del Curso (Diapositiva 1)]]

Este apartado establece los cimientos del estudio y la bibliografía de referencia.

- **Bibliografía Principal:** El texto base es _Computer Networks_ (Redes de Computadoras), 6ta edición, de Tanenbaum, Feamster y Wetherall.
- **Estructura de Evaluación:** Se destaca la importancia de los tests semanales (50% de la nota parcial) y los laboratorios obligatorios utilizando la herramienta **Packet Tracer**.
- **Hoja de Ruta del Primer Parcial:** Incluye la Introducción (Capítulo 1) y la Capa Física (Capítulo 2). El segundo parcial cubre la Capa de Enlace de Datos (Capítulo 3), la Subcapa de Acceso al Medio (Capítulo 4) y el Protocolo **IPv4** (**Internet Protocol version 4** - Protocolo de Internet versión 4) (Capítulo 5).

## [[Diapositiva 2 - Guía de Estudio|2. Conceptos de Protocolos y Modelos de Referencia (Diapositiva 2)]]

Se definen las reglas que rigen la comunicación y las arquitecturas de red.

- **¿Qué es un Protocolo?:** Es un conjunto de reglas y normas para la comunicación. Se analiza bajo tres ejes:
    - **Sintaxis:** Estructura y formato de los datos (encabezados, campos).
    - **Semántica:** Significado de cada sección del mensaje.
    - **Temporización:** Velocidad y secuenciación de los datos.
- **Objetivos de Diseño:** Los protocolos buscan garantizar la **Confiabilidad** (detección de errores), **Asignación de Recursos** (control de flujo y congestión), **Capacidad de Evolución** (direccionamiento e internetworking) y **Seguridad** (confidencialidad y autenticación).
- **Estructura de Capas:** Se utiliza la técnica de ocultación de información donde cada capa añade su propio **Header** (Encabezado) al mensaje (Carga útil o **Payload**).
- **Modelos de Referencia:**
    - **OSI** (**Open Systems Interconnection** - Interconexión de Sistemas Abiertos): Modelo teórico de 7 capas (Física, Enlace, Red, Transporte, Sesión, Presentación, Aplicación).
    - **TCP/IP** (**Transmission Control Protocol/Internet Protocol** - Protocolo de Control de Transmisión/Protocolo de Internet): Arquitectura práctica de 4 o 5 capas que domina la Internet actual.
    - **Diferencias Clave:** OSI distingue claramente entre servicios, interfaces y protocolos; **TCP/IP** no lo hace de forma tan estricta pero sus protocolos son los más exitosos.

## 3. La Capa Física: Transmisión y Medios (Diapositivas 3 y 4)
[[Diapositiva 3 - Guía de estudio]], [[Diapositiva 4 - Guía de Estudio]]
Se estudia cómo los bits se convierten en señales físicas para viajar por el medio.

- **Bases Teóricas:** Se distingue entre **Datos** (entidades con significado) y **Señales** (representaciones eléctricas o electromagnéticas).
- **Tipos de Canales:** **Simplex** (una dirección), **Half-duplex** (**Semidúplex** - ambas direcciones pero no simultáneas) y **Full-duplex** (**Dúplex completo** - ambas direcciones simultáneamente).
- **Impedimentos en la Transmisión:**
    - **Atenuación:** Pérdida de potencia con la distancia.
    - **Distorsión:** Por retardo o atenuación diferencial.
    - **Ruido:** Térmico, de intermodulación, **Crosstalk** (**Diafonía**) e impulsivo (picos electromagnéticos).
- **Límites de Velocidad:** Definidos por los teoremas de **Nyquist** (para canales sin ruido) y **Shannon** (para canales con ruido térmico).
- **Modulación Digital:** Conversión de bits a señales analógicas mediante:
	- **ASK** (**Amplitude Shift Keying** - Modulación por Desplazamiento de Amplitud)
	- **FSK** (**Frequency Shift Keying** - Modulación por Desplazamiento de Frecuencia)
	- **PSK** (**Phase Shift Keying** - Modulación por Desplazamiento de Fase)
	- **QAM** (**Quadrature Amplitude Modulation** - Modulación de Amplitud en Cuadratura).
- **Multiplexación:** Compartición del medio mediante:
	- **FDM** (**Frequency Division Multiplexing** - Multiplexación por División de Frecuencia)
	- **TDM** (**Time Division Multiplexing** - Multiplexación por División de Tiempo)
	- **WDM** (**Wavelength Division Multiplexing** - Multiplexación por División de Longitud de Onda)
	- **CDM** (**Code Division Multiplexing** - Multiplexación por División de Código).
- **Espectro Expandido:** Técnicas para resistir interferencias como:
	- **FHSS** (**Frequency Hopping Spread Spectrum** - Espectro Ensanchado por Salto de Frecuencia)
	- **DSSS** (**Direct Sequence Spread Spectrum** - Espectro Ensanchado por Secuencia Directa).

## 4. Infraestructura de Red y Conmutación (Diapositiva 5)

Trata sobre la red telefónica y los métodos para mover datos a gran escala.

- **Red Telefónica (PSTN - Public Switched Telephone Network):** Uso de **Trunks** (**Troncales**) que transportan miles de flujos de datos mediante **TDM** y **FDM**.
- **Digitalización:** Uso de **PCM** (**Pulse Code Modulation** - Modulación por Codificación de Pulsos) para convertir voz analógica a digital mediante un **Codec** (**Codificador-Decodificador**).
- **Métodos de Conmutación:**
    - **Circuit Switching** (**Conmutación de Circuitos**): Ruta física dedicada, mensajes en orden, flujo constante, ineficiente para datos en ráfagas.
    - **Packet Switching** (**Conmutación de Paquetes**): Los mensajes se dividen en datagramas ruteados independientemente, más eficiente para tráfico de datos, permite **Store and Forward** (**Almacenamiento y Reenvío**).

## 5. Capa de Enlace de Datos: Control y Errores (Diapositivas 6 y 7)

Responsable de la transferencia confiable entre dos nodos adyacentes.

- **Funciones Principales:** **Encuadre** (dividir bits en tramas), **Control de errores** y **Control de flujo**.
- **Detección de Errores:**
    - **Bits de Paridad:** Simple o impar.
    - **Checksums** (**Sumas de Comprobación**): Usados en protocolos como **IP**.
    - **CRC** (**Cyclic Redundancy Check** - Verificación de Redundancia Cíclica): El método más robusto basado en polinomios generadores.
- **Corrección de Errores:** Uso de la **Distancia de Hamming** y códigos **FEC** (**Forward Error Correction** - Corrección de Errores hacia Adelante).
- **Protocolos de Ventana Deslizante:** Permiten el envío de múltiples tramas sin esperar **ACK** (**Acknowledgment** - Acuse de Recibo) inmediato. Incluyen:
	- **Go-Back-N** (**Retroceder N**)
	- **Selective Repeat** (**Repetición Selectiva**).
- **Piggybacking:** Técnica de incluir el acuse de recibo dentro de una trama de datos que viaja en sentido contrario para optimizar el ancho de banda.

## [[Diapositiva 8 - Guía de estudio|6. Subcapa MAC y Ethernet (Diapositiva 8)]]

Decide quién transmite en medios de acceso compartido.

- **MAC** (**Medium Access Control** - Control de Acceso al Medio): Subcapa inferior de la capa de enlace.
- **Asignación Dinámica del Canal:** Basada en supuestos como tráfico independiente y canal único.
- **Protocolos de Acceso:**
    - **ALOHA:** Puro (transmisión inmediata) y Ranurado (en intervalos de tiempo).
    - **CSMA** (**Carrier Sense Multiple Access** - Acceso Múltiple con Detección de Portadora): Escuchar antes de hablar.
    - **CSMA/CD** (**CSMA with Collision Detection** - CSMA con Detección de Colisiones): Base de la Ethernet clásica para detener la transmisión al detectar colisiones.
- **Ethernet (IEEE 802.3):** Evolución desde 10 Mbps hasta 100 Gbps. Uso de direcciones **MAC** de 48 bits y el algoritmo de **Backoff** (**Retroceso**) Exponencial Binario tras colisiones.
- **Conmutación:** Diferencia entre **Hubs** (**Concentradores** - un solo dominio de colisión) y **Switches** (**Conmutadores** - microsegmentación y dominios de colisión por puerto).

## [[Diapositiva 9 - Guía de Estudio|7. Redes Inalámbricas WiFi y PAN (Diapositiva 9)]]

Tecnologías sin cables basadas en ondas de radio.

- **WiFi (IEEE 802.11):**
	- Arquitecturas **BSS** (**Basic Service Set** - Conjunto de Servicio Básico) con un **AP** (**Access Point** - Punto de Acceso)
	- **ESS** (**Extended Service Set** - Conjunto de Servicio Extendido).
- **Control de Acceso:** Utiliza **CSMA/CA** (**CSMA with Collision Avoidance** - CSMA con Evitación de Colisiones) mediante detección física y virtual.
- **Variantes Físicas:**
	- 802.11b (DSSS)
	- 802.11a/g (OFDM)
	- 802.11n (**MIMO** - **Multiple Input Multiple Output** - Múltiple Entrada Múltiple Salida).
- **PAN** (**Personal Area Network** - Red de Área Personal):
	- Bluetooth
	- **RFID** (**Radio Frequency Identification** - Identificación por Radiofrecuencia) como **EPC Gen2**.

## [[Diapositiva 10 - Guía de Estudio|8. Puentes, STP y VLANs (Diapositiva 10)]]

Gestión avanzada de redes de área local.

- **Puentes/Switches:** Conectan múltiples **LANs** (**Local Area Networks** - Redes de Área Local) para manejar mayores cargas.
- **STP** (**Spanning Tree Protocol** - Protocolo de Árbol de Expansión): Algoritmo para evitar bucles infinitos en redes con caminos redundantes.
- **VLANs** (**Virtual LANs** - Redes de Área Local Virtuales): Segmentación lógica de una red física para mejorar la seguridad y reducir el tráfico de difusión.

## [[Diapositiva 11 - Guía de Estudio|9. Capa de Red e IPv4 (Diapositiva 11)]]

Ruteo de paquetes a través de subredes.

- **Protocolo IP** (**Internet Protocol** - Protocolo de Internet): Protocolo no orientado a conexión basado en datagramas.
- **Direccionamiento:** Estructura de direcciones **IPv4**, máscaras de subred y **Subnetting** (**Subredes**).
- **Protocolos de Apoyo:**
    - **ARP** (**Address Resolution Protocol** - Protocolo de Resolución de Direcciones): Traduce direcciones IP a direcciones MAC.
    - **ICMP** (**Internet Control Message Protocol** - Protocolo de Mensajes de Control de Internet): Reporte de errores y diagnóstico.
    - **NAT** (**Network Address Translation** - Traducción de Direcciones de Red): Permite usar direcciones privadas para acceder a la Internet pública.


---
