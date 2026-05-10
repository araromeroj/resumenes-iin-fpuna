Esta guía de estudio pormenorizada detalla los contenidos fundamentales presentados en la **Diapositiva 2**, la cual corresponde a la segunda parte de la introducción al curso de redes, integrando explicaciones técnicas de los materiales de apoyo.

## 1. Conceptos Fundamentales de Protocolos de Red

Un protocolo se define esencialmente como un conjunto de reglas y normas que los dispositivos deben cumplir para que la comunicación de datos sea posible dentro de una red. Para un análisis profundo de cualquier protocolo, se deben considerar tres ejes fundamentales:

- **Sintaxis:** Se refiere a la estructura y el formato de los datos, incluyendo la longitud de los encabezados, la disposición de los campos y las reglas de relleno.
- **Semántica:** Se ocupa del significado específico de cada sección, campo o encabezado dentro del mensaje.
- **Temporización:** Determina la velocidad de la comunicación y la secuenciación de los datos mediante el uso de temporizadores o **Timers**.

Todo mensaje a transmitir consta de un **Encabezado** (información de control) y la carga útil o **Payload** (el mensaje real).

---

## 2. Objetivos Principales del Diseño de Protocolos

El diseño de redes y sus protocolos persigue cuatro metas críticas para garantizar un funcionamiento eficiente y seguro:

### A. Confiabilidad

El objetivo es lograr que la red opere correctamente a pesar de que sus componentes individuales (hardware o software) puedan no ser confiables. Esto incluye la implementación de mecanismos de detección y corrección de errores en los mensajes, así como protocolos de enrutamiento que permitan a los routers tomar decisiones automáticas para encontrar caminos alternativos si un enlace falla.

### B. Asignación de Recursos

Se busca crear diseños escalables que funcionen bien a medida que la red crece. Para esto se utilizan técnicas como:

- **Multiplexado Estadístico:** Compartir recursos de transmisión basados en las estadísticas reales de demanda.
- **Control de Flujo:** Evitar que un emisor rápido sature la capacidad de procesamiento de un receptor más lento.
- **Control de Congestión:** Gestionar situaciones donde demasiadas computadoras intentan enviar tráfico simultáneamente, saturando la red.
- **Calidad de Servicio (QoS - Quality of Service):** Mecanismos para priorizar tramas según su importancia o sensibilidad al retardo.

### C. Capacidad de Evolución

La red debe estar diseñada para permitir cambios y mejoras tecnológicas a lo largo del tiempo. Esto se logra mediante estructuras de capas que ocultan detalles de implementación y el uso de direccionamiento estandarizado. El concepto de **Internetworking** es vital aquí, ya que permite la interconexión de tecnologías de red heterogéneas.

### D. Seguridad

Consiste en defender la red mediante mecanismos de **confidencialidad** para evitar la escucha no autorizada (**eavesdropping**), así como técnicas de **autenticación** y de **integridad de datos** para asegurar que el remitente sea quien dice ser y que el mensaje no haya sido alterado.

---

## 3. Principios de Estratificación y Capas

La estratificación es el método estructural principal para dividir la funcionalidad compleja de una red en módulos manejables.

- **Comunicación entre Pares:** Cada instancia de un protocolo en una capa específica se comunica virtualmente con su homólogo (par) en otra máquina.
- **Interfaces:** Los servicios de las capas inferiores se acceden a través de interfaces bien definidas.
- **Encapsulamiento:** Cada capa añade su propio encabezado con información de control al mensaje recibido de la capa superior antes de pasarlo a la inferior; al recibirlo, el proceso se invierte y el encabezado se remueve.

### Aspectos de Diseño en las Capas:

1. **Direccionamiento:** Necesario para identificar a emisores y receptores mediante campos de dirección de origen y destino.
2. **Control de Errores:** Uso de bits de redundancia para detectar o corregir fallos de transmisión.
3. **Numeración:** Secuenciar mensajes mediante campos de número de secuencia para su reordenamiento posterior.
4. **Control de Flujo:** Uso de técnicas como la "ventana deslizante" para regular la velocidad de envío.
5. **Segmentación:** Mecanismos para dividir mensajes largos en fragmentos más pequeños y volver a ensamblarlos mediante indicadores como "más fragmentos".
6. **Multiplexado:** Permitir que una misma conexión o medio transporte múltiples conversaciones independientes.
7. **Enrutamiento:** Dirigir los paquetes a través de redes complejas.

---

## 4. Servicios de Red y su Diferencia con los Protocolos

Es fundamental distinguir entre lo que una capa ofrece y cómo se comunica con sus iguales.

- **Servicio:** Es el conjunto de primitivas u operaciones que una capa proporciona a la capa inmediatamente superior. Define "qué" puede hacer la capa, pero no el "cómo".
- **Protocolo:** Es el conjunto de reglas que rigen el formato y el significado de los mensajes intercambiados entre entidades iguales (pares) dentro de una misma capa. Las entidades implementan protocolos para hacer realidad sus definiciones de servicio.

### Tipos de Servicios:

1. **Orientado a la Conexión:** Similar a una llamada telefónica; requiere tres pasos (establecimiento, transmisión y desconexión) y una negociación previa de parámetros.
2. **Sin Conexión:** Similar a un telegrama; no requiere conexión previa y cada mensaje (llamado **datagrama**) contiene toda la información necesaria para llegar a su destino.

---

## 5. Modelo de Referencia OSI (Open Systems Interconnection)

El modelo **OSI** (**Open Systems Interconnection** - Interconexión de Sistemas Abiertos) fue propuesto por la **ISO** (**International Organization for Standardization** - Organización Internacional de Normalización) en 1983 y revisado en 1995. Es un modelo teórico de referencia que no especifica protocolos propios, pero sirve para definir arquitecturas de red con conceptos claros.

**Capas del modelo OSI:**

1. **Física:** Transmisión de bits puros, voltajes, cables y conectores.
2. **Enlace de Datos:** Transforma el medio en una línea libre de errores, gestionando tramas, control de flujo y direccionamiento físico.
3. **Red:** Gestiona el enrutamiento de paquetes y el direccionamiento lógico global.
4. **Transporte:** Entrega de datos de extremo a extremo, fragmentación y multiplexado, volviendo la red transparente para los hosts.
5. **Sesión:** Control del diálogo (tokens, dúplex) y puntos de recuperación. Ejemplo: protocolo **RPC** (**Remote Procedure Call** - Llamada a Procedimiento Remoto).
6. **Presentación:** Sintaxis y semántica de los datos, codificación de caracteres, cifrado y compresión (ej. ZIP).
7. **Aplicación:** Interfaz directa con la aplicación del usuario. Ejemplo: **HTTP** (**Hypertext Transfer Protocol** - Protocolo de Transferencia de Hipertexto).

**Unidades de Información por Capa:** Bits (Física), Tramas (Enlace), Paquetes (Red), Segmentos (Transporte).

---

## 6. Modelo de Referencia TCP/IP (Transmission Control Protocol/Internet Protocol)

El modelo **TCP/IP** (**Transmission Control Protocol/Internet Protocol** - Protocolo de Control de Transmisión/Protocolo de Internet) tiene un origen práctico y es la base de la Internet actual.

**Capas del modelo TCP/IP:**

1. **Enlace:** Describe cómo los enlaces (como Ethernet) deben satisfacer las necesidades de la capa superior.
2. **Inter-red (Internet):** Capa sin conexión cuyo objetivo es inyectar paquetes (**IP** - **Internet Protocol**) que viajan por las subredes. Incluye el protocolo **ICMP** (**Internet Control Message Protocol** - Protocolo de Mensajes de Control de Internet) para apoyo.
3. **Transporte:** Permite la conversación entre hosts de origen y destino mediante dos protocolos principales:
    - **TCP** (**Transmission Control Protocol** - Protocolo de Control de Transmisión): Confiable y orientado a conexión.
    - **UDP** (**User Datagram Protocol** - Protocolo de Datagramas de Usuario): No confiable y sin conexión.
4. **Aplicación:** Contiene protocolos de alto nivel como **SMTP** (**Simple Mail Transfer Protocol** - Protocolo Simple de Transferencia de Correo), **FTP** (**File Transfer Protocol** - Protocolo de Transferencia de Archivos) y **Telnet**.

---

## 7. Comparativa y Estandarización de Redes

- **Crítica:** El modelo OSI es excelente como referencia teórica pero su adopción se estancó por complejidad. TCP/IP tiene protocolos muy exitosos pero su modelo teórico es pobre y no distingue claramente las capas física y de enlace.
- **Estandarización:** Los estándares aseguran la interoperabilidad entre fabricantes. Ejemplos incluyen la **WiFi Alliance**, la **ONF** (**Open Networking Foundation** - Fundación de Redes Abiertas) para **SDN** (**Software Defined Networks** - Redes Definidas por Software), y organismos como la **ITU** (**International Telecommunication Union** - Unión Internacional de Telecomunicaciones) y la **ISO**. Existen estándares **de facto** y **de jure**.

---

## 8. Cuestiones Políticas, Legales y Sociales

El impacto de las redes va más allá de lo técnico, planteando retos como la **desinformación** (noticias falsas o "fake news"). Los desafíos para los operadores de plataformas incluyen definir la desinformación, detectarla confiablemente y decidir qué acciones tomar una vez identificada.

---

## 9. Unidades de Medida en Redes

Es crucial distinguir el uso de las potencias según el contexto:

- **Tasas de Bits:** Se utilizan potencias de 10 (ej. 1 Mbps = 1,000,000 bps).
- **Almacenamiento:** Se utilizan potencias de 2 (ej. 1 KB = 1024 bytes).
- **Nomenclatura:** Se usa "B" para bytes y "b" para bits.