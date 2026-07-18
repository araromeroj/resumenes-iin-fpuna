Esta guía de estudio detalla los conceptos clave de la **Diapositiva 10** y el material de apoyo de Tanenbaum sobre la interconexión de redes mediante puentes, el control de bucles y la segmentación lógica mediante redes virtuales.

---

## 1. Conmutación en la Capa de Enlace y Usos de los Puentes

Los **puentes (Bridges)**, actualmente conocidos de forma comercial como **Switches (Conmutadores)**, son dispositivos que operan en la capa de enlace de datos para unir múltiples **LAN (Local Area Network - Red de Área Local)** físicas en una única red lógica.

- **Motivos para su uso:**
    - **Interacción:** Permitir que redes establecidas previamente se comuniquen entre sí.
    - **Distribución geográfica:** Conectar redes situadas en diferentes edificios o plantas.
    - **Gestión de carga:** Dividir una red grande en segmentos independientes para manejar un tráfico mayor sin saturar el medio.
- **Puentes Transparentes:** La meta es que el puente sea invisible para los hosts; es decir, que no requiera cambios en el hardware o software de las estaciones para funcionar.

---

## 2. Puentes de Aprendizaje (Learning Bridges)

Un puente de aprendizaje construye su propia inteligencia para decidir si debe reenviar o descartar una trama, evitando inundar la red innecesariamente.

- **Dominio de Broadcast (Difusión):** Todas las **LAN (Local Area Network - Red de Área Local)** interconectadas por puentes transparentes forman un único dominio de difusión, donde las tramas enviadas a todos los nodos llegan a cada rincón de la red.
- **Algoritmo de Aprendizaje hacia Atrás (Backward Learning):**
    - El puente funciona en modo promiscuo, viendo todas las tramas que pasan por sus puertos.
    - Lee la dirección **MAC (Medium Access Control - Control de Acceso al Medio)** de origen de cada trama entrante y la anota en su **Tabla CAM (Content Addressable Memory - Memoria Direccionable por Contenido)** junto con el puerto por el que llegó.
    - Incluye un temporizador (**timer**) para cada entrada; si una estación no envía tramas durante unos minutos, su dirección es eliminada para reflejar cambios en la topología.
- **Algoritmo de Retransmisión (Forwarding):**
    - Cuando llega una trama, el puente busca la dirección **MAC (Medium Access Control - Control de Acceso al Medio)** de destino en su tabla.
    - Si el destino está en el mismo puerto por donde entró la trama, esta se descarta.
    - Si el destino es conocido y está en otro puerto, la trama se envía únicamente por ese puerto.
    - Si el destino es desconocido o es una dirección de difusión (`FF:FF:FF:FF:FF:FF`), el puente realiza una **inundación (flooding)**, enviando la trama por todos sus puertos excepto por el de entrada.

---

## 3. Protocolo de Árbol de Expansión (STP - Spanning Tree Protocol)

Para aumentar la fiabilidad, las redes suelen incluir enlaces redundantes. Sin embargo, esto crea bucles infinitos de tramas que pueden colapsar la red.

- **Problema de los bucles:** Una trama con destino desconocido entrará en un ciclo eterno al ser copiada y reenviada de puente en puente a través de los caminos paralelos.
- **Funcionamiento del STP (Spanning Tree Protocol - Protocolo de Árbol de Expansión):** Definido en el estándar **IEEE (Institute of Electrical and Electronics Engineers - Instituto de Ingenieros Eléctricos y Electrónicos) 802.1D**, este algoritmo reduce la topología física a un árbol lógico sin bucles.
- **Conceptos Críticos:**
    - **Puente Raíz (Root Bridge):** Es el puente con el identificador más bajo de la red, elegido como centro de la jerarquía.
    - **Puerto Raíz (Root Port):** El puerto de cada puente (que no sea el raíz) con el camino de menor costo hacia el puente raíz.
    - **Puerto Designado (Designated Port):** Puerto encargado de reenviar tráfico hacia un segmento de red específico.
    - **Puerto Bloqueado:** Puertos que no forman parte del árbol de expansión y se mantienen desactivados para evitar bucles.
- **Evolución:** El **Rapid Spanning Tree (Protocolo de Árbol de Expansión Rápido)** - **IEEE (Institute of Electrical and Electronics Engineers - Instituto de Ingenieros Eléctricos y Electrónicos) 802.1W** permite una convergencia más veloz ante cambios en la topología.

---

## 4. Dispositivos de Networking en cada Capa

Es fundamental distinguir en qué nivel del modelo **OSI (Open Systems Interconnection - Interconexión de Sistemas Abiertos)** opera cada dispositivo:

- **Capa 1 (Física):** **Repetidores** y **Hubs (Concentradores)**. Solo mueven bits de un cable a otro, amplificando la señal; no entienden direcciones ni tramas.
- **Capa 2 (Enlace):** **Puentes** y **Switches (Conmutadores)**. Operan con direcciones **MAC (Medium Access Control - Control de Acceso al Medio)** y dividen la red en dominios de colisión independientes.
- **Capa 3 (Red):** **Routers (Enrutadores)** y **Switches de Capa 3**. Utilizan direcciones **IP (Internet Protocol - Protocolo de Internet)** para dirigir paquetes a través de múltiples saltos entre diferentes redes.
- **Capa Superior:** **Application Gateways (Pasarelas de Aplicación)**. Entienden el contenido de los datos y pueden traducir formatos entre aplicaciones distintas.

---

## 5. Redes LAN Virtuales (VLANs)

Las **VLAN (Virtual Local Area Network - Red de Área Local Virtual)** permiten segmentar una red física en varias redes lógicas independientes, desacoplando la estructura organizativa de la disposición física de los cables.

- **Problema del Tráfico Broadcast:** En una red grande, las tramas de difusión llegan a todas las **CPU (Central Processing Unit - Unidad Central de Procesamiento)** de los hosts, consumiendo recursos innecesarios. Las **VLAN (Virtual Local Area Network - Red de Área Local Virtual)** resuelven esto limitando el alcance de estas tramas.
- **Objetivos de la Implementación:**
    1. **Rendimiento:** Reducir el tráfico de difusión innecesario.
    2. **Seguridad:** Aislar grupos de usuarios (ej. finanzas vs. invitados) para que no puedan espiar sus datos mutuos.
    3. **Flexibilidad:** Cambiar a un usuario de red mediante software sin tener que mover cables físicamente.
- **Asignación de Puertos:**
    - **Estática:** El administrador configura manualmente qué puerto pertenece a qué **VLAN (Virtual Local Area Network - Red de Área Local Virtual)** (método más común).
    - **Dinámica:** Basada en la dirección **MAC (Medium Access Control - Control de Acceso al Medio)** de la estación o mediante autenticación de usuario.
- **Enlaces Troncales (Trunk Links) y Estándar IEEE 802.1Q:**
    - Cuando las tramas de varias **VLAN (Virtual Local Area Network - Red de Área Local Virtual)** deben viajar por un solo cable entre dos switches, se usa un **Trunk (Enlace Troncal)**.
    - Para no mezclar el tráfico, se añade una **etiqueta (tag)** a la trama Ethernet según el estándar **IEEE (Institute of Electrical and Electronics Engineers - Instituto de Ingenieros Eléctricos y Electrónicos) 802.1Q**.
    - Esta etiqueta incluye el **VLAN ID (Virtual LAN Identifier - Identificador de LAN Virtual)**, un campo de 12 bits que permite identificar hasta 4,096 redes distintas.