Esta guía de estudio resume los conceptos clave presentados en la **Diapositiva 8**, complementada con información técnica del libro de texto de Tanenbaum, sobre la subcapa **MAC (Medium Access Control - Control de Acceso al Medio)** y la tecnología **Ethernet (IEEE 802.3)**.
## 1. La Subcapa MAC (Medium Access Control - Control de Acceso al Medio)

La subcapa **MAC** es la parte inferior de la capa de enlace de datos y tiene la responsabilidad crítica de decidir qué dispositivo es el siguiente en transmitir dentro de un canal de comunicación compartido o enlace de acceso múltiple.

- **Arquitectura Jerárquica:** Se sitúa justo encima de la Capa Física y por debajo de la subcapa **LLC** (**Logical Link Control** - Control de Enlace Lógico). Mientras que la **LLC** se encarga de la gestión de enlaces lógicos, la **MAC** gestiona el acceso físico al medio.
- **Importancia en LANs:** Es especialmente vital en redes de área local (**LANs** - **Local Area Networks**), ya que muchas de ellas (como WiFi o Ethernet clásico) son canales de difusión donde múltiples estaciones compiten por el mismo ancho de banda.

## 2. El Problema de Asignación del Canal

El objetivo es determinar cómo repartir el ancho de banda entre los emisores.

- **Asignación Estática:** Utiliza técnicas tradicionales como **FDM** (**Frequency Division Multiplexing** - Multiplexación por División de Frecuencia) o **TDM** (**Time Division Multiplexing** - Multiplexación por División de Tiempo).
	- **Características:** El ancho de banda se divide en porciones fijas para cada usuario.
	- **Desventaja:** Es ineficiente para el tráfico de datos de computadoras, que suele ser en ráfagas. Si un usuario no tiene nada que enviar, su porción de ancho de banda simplemente se pierde, mientras que otros podrían estar bloqueados por falta de recursos.
- **Asignación Dinámica:** El canal se asigna bajo demanda únicamente a los usuarios que necesitan transmitir en ese momento.
	- **Ventaja:** Potencialmente hasta N veces más eficiente en sistemas con muchos emisores activos de forma intermitente.
	- **Supuestos Clave para el Diseño de Protocolos Dinámicos****:**
	    1. **Tráfico independiente:** Las estaciones generan tramas de forma autónoma (modelo de Poisson).
	    2. **Canal único:** Un solo medio físico para todas las comunicaciones; no hay canales externos de coordinación.
	    3. **Detección de portadora:** Capacidad de la estación para saber si el canal está ocupado antes de transmitir.
	    4. **Colisiones observables:** Las estaciones notan si dos o más transmisiones ocurren simultáneamente.
	    5. **Tiempo (Continuo vs. Ranurado):** Las transmisiones pueden iniciar en cualquier momento o solo al inicio de intervalos fijos llamados **Slots** (Ranuras).

## 3. Protocolos de Acceso Múltiple

Estos algoritmos ponen orden en el caos potencial de una red compartida.
**A. ALOHA**
- **Puro:** Las estaciones transmiten siempre que tienen datos. Si hay colisión, esperan un tiempo aleatorio y reintentan. Eficiencia máxima del 18%.
- **Ranurado:** El tiempo se divide en intervalos. Las estaciones solo transmiten al inicio de una ranura. Esto reduce el periodo vulnerable a la mitad y duplica la eficiencia al 37%.
**B. CSMA (Carrier Sense Multiple Access - Acceso Múltiple con Detección de Portadora)**
Las estaciones "escuchan antes de hablar".
- **1-persistente:** Transmite en cuanto detecta el canal libre. Si está ocupado, espera continuamente y transmite apenas se libere.
- **No-persistente:** Si el canal está ocupado, espera un tiempo aleatorio y vuelve a detectar. Reduce colisiones pero aumenta el retardo.
- **p-persistente:** En canales ranurados, transmite con probabilidad p si el canal está libre.
**C. CSMA/CD (Collision Detection - Detección de Colisiones)**
Es la mejora sobre **CSMA** que detiene la transmisión inmediatamente al detectar una colisión, ahorrando ancho de banda.
- **Regla de Tiempo:** El tiempo mínimo para detectar una colisión es 2τ, donde τ es el tiempo de propagación de un extremo a otro del cable. Esto define el tamaño de la **trama mínima** en Ethernet (64 bytes) para asegurar que el emisor note la colisión antes de terminar de enviar.
**D. Protocolos Libres de Colisiones y de Contención Limitada**
- **Mapeo de bits (Bitmap):** Las estaciones reservan turnos en una ranura de contención previa a los datos.
- **Token ring:** El token enviado por el anillo define el orden en el que se va a transmitir. La estación con el token puede enviar una trama antes de pasar el turno.
- **Cuenta atrás binaria (Binary Countdown):** Se usan las direcciones de las estaciones (bits) para arbitrar quién gana el canal sin colisiones.
- **Árbol adaptativo:** Divide las estaciones en grupos jerárquicos (nodos de un árbol) para gestionar el acceso según la carga de la red. (es de contención limitada)

## 4. Redes Ethernet (IEEE 802.3)

Ethernet es la tecnología predominante para redes cableadas.

**Trama Ethernet (Frame Format):**
1. **Preámbulo + SFD (8 bytes):** Patrón para sincronizar relojes, el sfd es la bandera de inicio de trama.
2. **Dirección Destino y Origen (6 bytes cada una):** Direcciones físicas únicas de 48 bits.
3. **Tipo/Longitud (2 bytes):** Indica el protocolo superior (ej. **IPv4** - **Internet Protocol version 4**) o el tamaño de la carga.
4. **Datos (Payload):** El paquete de red (desde 46 bytes hasta 1500 bytes).
5. **Relleno (Pad):** Asegura que la trama alcance los 64 bytes mínimos.
6. **Checksum (CRC - Cyclic Redundancy Check):** Valor de 32 bits para detectar errores de bits.

- **Ethernet Clásico (Capa Física y MAC):** Utiliza **CSMA/CD (Carrier Sense Multiple Access with Collision Detection - Acceso Múltiple con Detección de Portadora y Detección de Colisiones)** 1-persistente.
- **Algoritmo de Backoff Exponencial Binario (Retroceso Exponencial Binario):** Tras una colisión, la estación elige un tiempo de espera aleatorio entre 0 y $2^i - 1$ ranuras (donde $i$ es el número de colisiones). El límite de reintentos es 16.
- **Formato de la Trama Ethernet:** Incluye campos como el preámbulo, direcciones de origen y destino, tipo/longitud y el **CRC (Cyclic Redundancy Check - Verificación de Redundancia Cíclica)** para detección de errores.
- **Direcciones MAC (Media Access Control - Control de Acceso al Medio):** Son identificadores únicos grabados en la **NIC** (**Network Interface Card** - Tarjeta de Interfaz de Red).
    - Son de 48 bits (6 bytes).
    - **Unicast (Unidifusión):** Dirigido a una sola estación.
    - **Multicast (Multidifusión):** Dirigido a un grupo.
    - **Broadcast (Difusión):** Dirigido a todas las estaciones (`FF:FF:FF:FF:FF:FF`).
    - **OUI (Organizationally Unique Identifier - Identificador Único de Organización):** Los primeros 3 bytes que identifican al fabricante.

## 5. [[Ethernet Conmutado|Ethernet Conmutado (Switched Ethernet)]]

- **Hub:** Es un dispositivo de Capa 1 (Física). Simplemente repite los bits por todos los puertos. Todas las estaciones comparten el mismo **dominio de colisión** y deben usar **CSMA/CD**.
- **Switch:** Es un dispositivo de Capa 2 (Enlace). Analiza las direcciones **MAC**. Cada puerto es un **dominio de colisión** independiente. Permite transmisiones **Full-Duplex** (Dúplex Completo), eliminando las colisiones por completo si se usa conmutación dedicada.
- **Hubs vs. Switches:** En un **Hub (Concentrador)** todas las líneas comparten el mismo dominio de colisión. Un **Switch (Conmutador)** aísla cada puerto en un dominio separado, permitiendo transmisiones **Full-Duplex (Dúplex Completo)** sin colisiones.
- **Tabla CAM (Content Addressable Memory - Memoria Direccionable por Contenido):** El switch asocia direcciones MAC con puertos físicos mediante un algoritmo de aprendizaje hacia atrás.
- **Modos de trabajo del Switch:**
    1. **Cut-through (Corte a través):** El switch lee la dirección de destino y empieza a retransmitir inmediatamente, aún antes de recibir toda la trama.
    2. **Free of segments (Libre de segmentos):** Espera a recibir el byte 64 (es decir, en el byte numero 65 recién empieza) para asegurar que no sea un segmento de trama proveniente de una colisión.
    3. **Store and forward (Almacenamiento y reenvío):** Recibe toda la trama, la almacena, verifica el **CRC** y luego la envía al puerto de destino. Es el más seguro pero lento.

## 6. Evolución de Ethernet

- **Fast Ethernet (IEEE 802.3u):** Transmite a 100 Mbps manteniendo la compatibilidad con tramas de 64 bytes.
    - **100Base-TX:** Utiliza dos pares de cables **UTP (Unshielded Twisted Pair - Par Trenzado No Blindado)** Categoría 5.
    - **100Base-T4:** Utiliza cuatro pares de cables **UTP (Unshielded Twisted Pair - Par Trenzado No Blindado)** Categoría 3.
- **Gigabit Ethernet:** Evolución a 1000 Mbps.