# Conceptos Generales y Evolución

Las redes de computadoras se definen como un conjunto de computadoras autónomas interconectadas mediante una sola tecnología.

## Evolución de la Telefonía Celular

- **1G**: Transmisión de voz analógica.
    
- **2G**: Introducción de voz digital para mayor capacidad y seguridad; surge el estándar **GSM**.
    
- **3G**: Servicios de voz y datos digitales de banda ancha.
    
- **4G (LTE)**: Mejora significativa en las tasas de bits; se convierte en el estándar predominante de acceso a internet.
    
- **5G**: Promete tasas de hasta 10 Gbps, desplegado masivamente a partir de 2020.

## Redes Inalámbricas (WiFi)

- Basadas en el estándar **IEEE 802.11**.
    
- Utilizan bandas de frecuencia "sin licencia".
    
- **Modos de operación**: _Ad hoc_ (directo entre dispositivos) y con _Punto de Acceso_ (AP).
    
- Las señales sufren de **Multipath Fading** (reflexiones), lo que requiere esquemas complejos como **OFDM**.

---

# Protocolos de Red

Un protocolo es un conjunto de reglas y normas que permiten la comunicación de datos.

## Elementos de un Protocolo

1. **Sintaxis**: Formato de los datos, longitudes de campos y reglas de relleno.
    
2. **Semántica**: Significado de cada sección del encabezado o mensaje.
    
3. **Temporización**: Control de tiempos (timers) para la transmisión.
## Objetivos de Diseño

- **Confiabilidad**: Operar correctamente a pesar de componentes no confiables (detección/corrección de errores).
    
- **Asignación de Recursos**: Gestión del ancho de banda y priorización.
    
- **Evolución**: Capacidad de la red para crecer y cambiar tecnologías.
    
- **Seguridad**: Protección contra accesos no autorizados y ataques. 

---
# Modelos de Referencia

Los modelos dividen las funciones de red en capas para reducir la complejidad.

## Modelo OSI (7 Capas)

1. **Física**: Transmisión de bits por el canal.
    
2. **Enlace de Datos**: Transmisión libre de errores entre nodos adyacentes (tramas).
    
3. **Red**: Encaminamiento de paquetes desde el origen al destino.
    
4. **Transporte**: Comunicación extremo a extremo y control de flujo.
    
5. **Sesión**: Gestión de diálogos entre aplicaciones.
    
6. **Presentación**: Sintaxis y semántica de la información (compresión, cifrado).
    
7. **Aplicación**: Interfaz con el usuario final (HTTP, FTP).

## Modelo TCP/IP (4 Capas)

1. **Enlace (Host-to-Network)**: Interfaz con el hardware.
    
2. **Internet**: IP (Internet Protocol), manejo de paquetes y ruteo.
    
3. **Transporte**: TCP (orientado a conexión) y UDP (sin conexión).
    
4. **Aplicación**: Protocolos de alto nivel.

---

# Unidades de Medida y Estándares

## Reglas de Medición

- **Tasas de bits**: Se utilizan potencias de 10 ($1\text{ Mbps} = 10^6\text{ bps}$).
    
- **Almacenamiento**: Se utilizan potencias de 2 ($1\text{ KiB} = 2^{10}\text{ bytes}$).

## Estandarización

- **ITU (International Telecommunication Union)**: Estándares de telecomunicaciones.
    
- **IEEE (Institute of Electrical and Electronics Engineers)**: Estándares de redes locales (802.3 Ethernet, 802.11 WiFi).
    
- **IETF (Internet Engineering Task Force)**: Publica los **RFC** (Request for Comments) que definen los protocolos de Internet.

---

# Asuntos Políticos, Legales y Sociales

## Neutralidad de la Red

Principio que establece que los ISPs deben tratar todo el tráfico de Internet por igual, sin discriminar por contenido, aplicación o dispositivo.

- **Zero Rating**: Práctica donde el ISP no cobra por el uso de datos de aplicaciones específicas (ej. WhatsApp gratis), lo cual es controversial respecto a la neutralidad.

## Seguridad y Privacidad

- **Ataques DDoS**: Uso de botnets (muchas veces dispositivos IoT inseguros) para saturar servicios.
    
- **Phishing**: Suplantación de identidad para robo de datos.
    
- **Profiling/Tracking**: Seguimiento del comportamiento del usuario mediante cookies y huellas digitales del navegador (_browser fingerprinting_).

### Desinformación

El desafío de las **Fake News** y cómo las plataformas detectan o gestionan la información falsa sin vulnerar la libertad de expresión.

---

## Enlaces relacionados

- [[Modelo OSI]]
    
- [[Modelo TCP-IP]]
    
- [[Protocolos de Red]]
    
- [[Neutralidad de la Red]]
    
- [[Estándares IEEE]]
    
- [[Seguridad Informática]]