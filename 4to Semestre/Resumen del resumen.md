**Redes:** conjuntos de dispositivos informáticos interconectados y autónomos para intercambiar información a través de medios de transmisión.

**Usos de las redes de computadoras:**
- Entretenimiento (streamming, música)
- Acceso a la información (wikipedia, el rincón del vago)
	- Modelo cliente servidor: el cliente solicita información a través de un servidor.
- Internet de las cosas (domótica, casas inteligentes, electrodomésticos)
	- **Computación Ubicua:** la que está adherida a la vida o a la cotidianeidad.
- Comunicación P2P (whatsapp, mensajes de texto, llamadas)
- Comercio Electrónico (alibaba, aliexpress, marketplace)

**Tipos de redes:**
- **Acceso de Banda ancha:** alta velocidad, uso doméstico, usan cables coaxiales y fibra óptica.
- **Acceso móviles e inalámbricas:** las inalámbricas (802.11) son de menor alcance
	- Ejemplos: GPS, NFC, sensores, M-commerce, parquímetros
- **Proveedoras de Contenido (CDN):** conjunto grande de servidores distribuidos geográficamente
	- Ejemplo: Servicios de Internet desde la nube
- **De tránsito (BACKBONE):** Transportan tráfico entre el ISP y el proveedor de contenido aunque no estén directamente conectados.
- **Corporativas:** Permite compartir información entre dispositivos de una misma compañía.
	- Ejemplo: Voice over IP, Telefonía IP, negocios electrónicos, VPN´s (Virtual Private Networks - conectan redes de diferentes sitios en una sola red lógica, sirve para la comunicación entre empleados).

**Tecnología de redes**
- **PAN (vecindad o personal):** Red de área personal, conexión de periféricos, alcance de pocos metros.
	- Ejemplo: Bluetooth, redes de sensores.
- **LAN (edificio o campus):** Alta velocidad, medio compartido, usa cables o canal inalámbrico.
	- Es la red corporativa en una compañía, paquetes de software de gestión de dispositivos, wifi, redes domésticas (facil, segura, confiable, barata).
- **MAN (ciudad):** alcance de una ciudad, conecta los dispositivos de un área metropolitana.
	- Ejemplo: Cable TV, WiMax
- **WAN (país):** se extiende por un área geográfica amplia, son de proveedores (no pertenece a la compañía). Tiene dos componentes - routers y enlaces de transmisión. Hay dos tipos:
	- **Conmutación de circuitos:** Viene de compañías telefónicas (orientado a la conexión, fácil de implementar QoS, llegan en un orden distinto en que salieron).
	- **Conmutación de paquetes:** Viene de la comunidad de internet (redes sin conexión, dificil de implementar QoS, los mensajes llegan en el mismo orden de salida ).
	- Ejemplo: ISP
- **Interredes (planeta):** colección de redes interconectadas. Combina subredes y hosts: una subred puede ser una ISP y una interred puede ser como una WAN. La conexión se hace entre LANS o una LAN con una WAN.
	- **Gateways:** conexión entre dos o más redes

**Ejemplos de Redes**
- La Internet
- Redes Móviles (Arquitectura, conmutación de paquetes y de circuitos, redes móviles 4G)
- Redes Inalámbricas (WiFi)


**Protocolos de Red**
- **Protocolo:** Conjunto de reglas y normas que deben cumplir los dispositivos para la comunicación de datos en una red. Se intercambian las entidades en una sola capa. Las entidades implementan protocolos para implementar sus definiciones de servicio.
- **Cuestiones para el análisis de protocolos:**
	- Sintaxis: Longitudes de encabezados, campos, reglas de relleno.
	- Semántica: Significado de cada campo o encabezado.
	- Temporización: timers

**Objetivos de diseño de protocolos**
- Confiabilidad: que la red opere correctamente aunque esté conformado por componentes no confiables.
- Asignación de recursos: Calidad del servicio, problemas de congestión, multiplexado, diseños escalables.
- Capacidad de evolución: Usar estructura de capas para soportar cambios dividiendo el problema, usar direccionamiento, internetworking para tratar con distintas tecnologías de redes.
- Seguridad: confidencialidad, autenticación e integridad de datos

**Aspectos del diseño de capas**
- Direccionamiento: Identificar emisores y receptores.
	- Campos de dirección de origen y dirección de destino.
- Control de errores: Detección o corrección de errores.
	- Campos de bits de redundancia.
- Numeración: Forma de secuenciar los mensajes para posterior ordenamiento.
	- Campos de números de secuencia.
- Control de flujo: Evitar que un emisor rápido sature a receptores lentos.
	- Técnicas de ventanas deslizantes.
- Segmentación: Segmentar y reensamblar mensajes.
	- Campos de más fragmentos o último fragmento.
- Multiplexado: Misma conexión o medio de transmisión para múltiples conversacionws.
- Enrutamiento: Para dirigir o rutear paquetes a una red compleja.

**Servicio:** Conjunto de operaciones que una capa ofrece a otra superior. Define qué operaciones puede realizar, pero no dice cómo se implementan tales operaciones.

**Modelos OSI TCP IP**
- [*] **ISO - International Standards Organization**
- [*] **OSI - Open Systems Interconexion

**Modelo OSI - Capas**
1. Física: Transmitir bits a través del medio, provee especificaciones físicas y mecánicas. **ACÁ SON BITS**.
2. De Enlace: Organiza los bits en tramas, provee un medio de comunicación libre de errores. El direccionamiento es *físico* para identificar el origen y el destino de tramas. **ACÁ SON TRAMAS**.
3. Red: Mueve paquetes del origen al destino, provee el internetworking. El direccionamiento es *lógico*. **ACÁ SON PAQUETES**.
4. Transporte: Provee el envío de mensajes y recuperación de errores, determina el tipo de servicio que se proporciona a la capa superior. **ACÁ SON SEGMENTOS**.
5. Sesión: Establece y maneja sesiones entre máquinas, permite el control del diálogo y la recuperación ante fallas.
	- **RPC**
6. Presentación: Traduce, encripta y comprime datos. Define la sintaxis y la semántica de la información transmitida, codificación de caracteres, algoritmos de cifrado y compresión.
	- **ZIP**
7. Aplicación: Permite el acceso a los recursos de la red, interactúa con la aplicación del usuario.
	- **HTTP**
Estandarización
Unidades de Medidas