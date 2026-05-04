## 1. Redes LAN Inalámbricas WiFi (IEEE 802.11)
Es el tema principal de la primera parte de la diapositiva, centrándose en cómo se estructuran y operan estas redes.
- **Arquitectura de Red:**
    - **BSS (Basic Service Set):** La unidad básica de una red 802.11, compuesta por estaciones inalámbricas y, opcionalmente, un Punto de Acceso (AP).
    - **ESS (Extended Service Set):** Un conjunto de BSS conectados a través de un "Sistema de Distribución", permitiendo que los usuarios se muevan entre APs sin perder la conexión.
    - **SSID (Service Set Identifier):** Identificador de texto que nombra a la red inalámbrica.
    
- **Capas del Protocolo:**
    - **Capa Física:** Se profundiza en la compatibilidad de los NICs con múltiples estándares (802.11 a/b/g) y cómo la combinación de técnicas de **modulación** y **tasas de codificación** determinan la velocidad de bits (bitrate).
    - **Subcapa MAC:** Es común a las diferentes capas físicas y se encarga de gestionar el acceso al medio compartido.
        
- **Tipos de Tramas 802.11:**
    - **Tramas de Administración:** Gestionan la comunicación entre estaciones y APs. Incluyen conceptos como **asociación**, **autenticación**, **reasociación** y **tramas de baliza (beacons)**.
    - **Tramas de Datos:** Transportan la información del usuario. Una característica clave es que poseen entre **3 y 4 direcciones MAC** para permitir el paso de datos a través del AP.
    - **Tramas de Control:** Ayudan en la entrega de tramas de datos. Conceptos clave: **RTS** (Request to Send), **CTS** (Clear to Send), **ACK** (Agradecimiento) y **PS-Poll**.
    
- **Gestión de Energía:**
    - **Tramas de Baliza (Beacons):** Emisiones periódicas (típicamente cada 100 ms) del AP que anuncian su presencia y sincronizan parámetros del sistema.        
    - **APSD (Automated Power Save Delivery):** Técnica de ahorro de energía donde se definen periodos de servicio para que el cliente pueda entrar en modo de reposo y despertar solo cuando sea necesario recibir datos.
    
- **Servicios del Sistema:** Autenticación, Deautenticación, Privacidad, Distribución e Integración (conectar la red inalámbrica con una red cableada).

---
## 2. Redes PAN Inalámbricas Bluetooth (IEEE 802.15.1)
Se enfoca en redes de área personal de corto alcance.
- **Arquitectura Bluetooth:**
    - **Piconet:** Una red pequeña con un **Maestro** y hasta **7 Esclavos activos** (y hasta 255 en modo "estacionado"). Utiliza un sistema TDM (Multiplexación por División de Tiempo) controlado por el maestro.
    
- **Capa de Radio:**
    - Opera en la **banda ISM de 2.4 GHz**.
    - Utiliza **79 canales de 1 MHz**.
    - **Salto de Frecuencia (Frequency Hopping):** Realiza hasta 1600 saltos por segundo para evitar interferencias.
    
- **Clases de Potencia y Rango:**
	- **Clase 1:** 100 mW (~100 metros).
    - **Clase 2:** 2.5 mW (~10 metros).
    - **Clase 3:** 1 mW (~1 metro).
    - **Clase 4:** 0.5 mW (~0.5 metros).
    
- **Pila de Protocolos:**
    - **Capa de Control de Enlace (Banda Base):** Convierte el flujo de bits en tramas.
    - **Administrador de Enlace (Link Manager):** Gestiona canales lógicos, emparejamiento (pairing), encriptación y calidad de servicio (QoS).
    - **Perfiles:** Definen el soporte para aplicaciones específicas (ej. manos libres, transferencia de archivos).

---
## 3. Redes EPC Gen2 (RFID)
Aunque se menciona como el punto 4 de la agenda, se centra en la identificación por radiofrecuencia.
- **Concepto Central:** Protocolo de interfaz de aire para comunicaciones pasivas (sin batería en la etiqueta) entre un lector y etiquetas (tags) en la banda de UHF.
- **Profundización:** Se estudia cómo los lectores identifican múltiples objetos simultáneamente y cómo se gestionan las colisiones cuando muchas etiquetas responden al mismo tiempo (protocolos de inventario).

---
# Resumen de Conceptos Clave para el Examen:

1. **WiFi:** Diferencia entre BSS y ESS; propósito de las tramas RTS/CTS para evitar colisiones.    
2. **Ahorro de Energía:** Importancia de los Beacons y el modo APSD en dispositivos móviles.
3. **Bluetooth:** El concepto de Piconet y cómo el salto de frecuencia ayuda a la coexistencia en la banda ISM de 2.4 GHz.
4. **Capa Física vs MAC:** Cómo interactúan (una MAC única para múltiples físicas en WiFi).