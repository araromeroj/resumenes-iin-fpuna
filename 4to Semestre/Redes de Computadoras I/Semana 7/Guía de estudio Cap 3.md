Esta guía de estudio resume los conceptos clave presentados en la **Diapositiva 8**, complementada con información técnica del libro de texto de Tanenbaum, sobre la subcapa **MAC (Medium Access Control - Control de Acceso al Medio)** y la tecnología **Ethernet (IEEE 802.3)**.
## 1. La Subcapa MAC (Medium Access Control - Control de Acceso al Medio)

Esta subcapa es responsable de decidir qué dispositivo es el siguiente en transmitir dentro de un enlace de acceso múltiple.

- **Relación jerárquica:** Se ubica en la parte inferior de la Capa de Enlace de Datos, situándose por debajo de la subcapa **LLC (Logical Link Control - Control de Enlace Lógico)** y por encima de la Capa Física.

## 2. El Problema de Asignación del Canal

El objetivo es determinar cómo repartir el ancho de banda entre los emisores.

- **Asignación Estática:** Utiliza técnicas como **FDM (Frequency Division Multiplexing - Multiplexación por División de Frecuencia)** o **TDM (Time Division Multiplexing - Multiplexación por División de Tiempo)**. Es ineficiente para tráfico intermitente, ya que el ancho de banda se pierde si el usuario no transmite.
- **Asignación Dinámica:** El canal se asigna bajo demanda. Es potencialmente hasta $N$ veces más eficiente en sistemas con muchos emisores.
- **Supuestos clave para la asignación dinámica:**
    1. **Tráfico independiente:** Las estaciones generan tramas de forma autónoma.
    2. **Canal único:** Solo hay un medio para transmitir y recibir.
    3. **Detección de portadora:** Capacidad de saber si el canal está en uso antes de enviar datos.
    4. **Colisiones observables:** Capacidad de notar si dos o más transmisiones ocurren simultáneamente.

## 3. Protocolos de Acceso Múltiple

- **ALOHA:** Protocolo donde las estaciones transmiten cuando tienen datos. Incluye versiones como ALOHA puro y ALOHA ranurado.
- **CSMA (Carrier Sense Multiple Access - Acceso Múltiple con Detección de Portadora):** Las estaciones "escuchan" antes de transmitir.
    - **No-persistente:** Si el canal está ocupado, espera un tiempo aleatorio.
    - **p-persistente:** En canales ranurados, transmite con probabilidad $p$ si está libre.
- **CSMA/CD (Carrier Sense Multiple Access with Collision Detection - Acceso Múltiple con Detección de Portadora y Detección de Colisiones):** Base de la Ethernet clásica. Si se detecta una colisión, la transmisión se aborta inmediatamente para ahorrar ancho de banda y se espera un tiempo aleatorio para reintentar.
- **Protocolos libres de colisiones:** Ejemplos como el **Mapeo de bits (Bitmap)**, donde las estaciones reservan su turno en una ranura de contención.
- **Protocolos de contención limitada:** Como el **Árbol adaptivo**, que divide las estaciones en grupos para gestionar el acceso según la carga de la red.

## 4. Redes Ethernet (IEEE 802.3)

- **Ethernet Clásico (Capa Física y MAC):** Utiliza **CSMA/CD (Carrier Sense Multiple Access with Collision Detection - Acceso Múltiple con Detección de Portadora y Detección de Colisiones)** 1-persistente.
- **Algoritmo de Backoff Exponencial Binario (Retroceso Exponencial Binario):** Tras una colisión, la estación elige un tiempo de espera aleatorio entre 0 y $2^i - 1$ ranuras (donde $i$ es el número de colisiones). El límite de reintentos es 16.
- **Formato de la Trama Ethernet:** Incluye campos como el preámbulo, direcciones de origen y destino, tipo/longitud y el **CRC (Cyclic Redundancy Check - Verificación de Redundancia Cíclica)** para detección de errores.
- **Direcciones MAC (Media Access Control - Control de Acceso al Medio):**
    - Son de 48 bits (6 bytes).
    - **Unicast (Unidifusión):** Dirigido a una sola estación.
    - **Multicast (Multidifusión):** Dirigido a un grupo.
    - **Broadcast (Difusión):** Dirigido a todas las estaciones (`FF:FF:FF:FF:FF:FF`).
    - **OUI (Organizationally Unique Identifier - Identificador Único de Organización):** Los primeros 3 bytes que identifican al fabricante.

## 5. Ethernet Conmutado (Switched Ethernet)

- **Hubs vs. Switches:** En un **Hub (Concentrador)** todas las líneas comparten el mismo dominio de colisión. Un **Switch (Conmutador)** aísla cada puerto en un dominio separado, permitiendo transmisiones **Full-Duplex (Dúplex Completo)** sin colisiones.
- **Tabla CAM (Content Addressable Memory - Memoria Direccionable por Contenido):** El switch asocia direcciones MAC con puertos físicos mediante un algoritmo de aprendizaje hacia atrás.
- **Modos de trabajo del Switch:**
    1. **Cut-through (Corte a través):** Retransmite en cuanto lee la dirección de destino.
    2. **Free of segments (Libre de segmentos):** Espera a recibir 64 bytes para evitar fragmentos de colisión.
    3. **Store and forward (Almacenamiento y reenvío):** Recibe toda la trama y verifica el **CRC (Cyclic Redundancy Check - Verificación de Redundancia Cíclica)** antes de enviarla.

## 6. Evolución de Ethernet

- **Fast Ethernet (IEEE 802.3u):** Transmite a 100 Mbps manteniendo la compatibilidad con tramas de 64 bytes.
    - **100Base-TX:** Utiliza dos pares de cables **UTP (Unshielded Twisted Pair - Par Trenzado No Blindado)** Categoría 5.
    - **100Base-T4:** Utiliza cuatro pares de cables **UTP (Unshielded Twisted Pair - Par Trenzado No Blindado)** Categoría 3.
- **Gigabit Ethernet:** Evolución a 1000 Mbps.