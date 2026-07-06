## HUB (Concentrador)

**Significado de la palabra:** La palabra inglesa _Hub_ se traduce como "cubo" o "centro de actividad" (como el eje de una rueda donde convergen los radios). En redes, actúa como un punto de conexión central.

**Concepto y Características:**

- **Capa del Modelo OSI:** Opera en la **Capa 1 (Física)**. No entiende de direcciones MAC ni de paquetes; solo ve señales eléctricas o bits.
- **Funcionamiento (Broadcast por defecto):** Cuando un Hub recibe un paquete de datos en uno de sus puertos, lo **replica y envía a todos los demás puertos** sin distinción. El dispositivo de destino acepta el paquete y los demás lo descartan.
- **Dominio de Colisión:** Todos los puertos del Hub comparten un **único dominio de colisión**. Si dos dispositivos transmiten al mismo tiempo, los datos chocan y deben retransmitirse.
- **Ancho de Banda compartido:** Si tienes un Hub de 100 Mbps y 10 dispositivos conectados, esos 100 Mbps se reparten entre todos cuando hay tráfico simultáneo.
- **Seguridad:** Baja, ya que cualquier dispositivo conectado puede "escuchar" el tráfico de los demás.

## SWITCH (Conmutador)

**Significado de la palabra:** La palabra _Switch_ significa "interruptor" o "conmutador". Su nombre proviene de su capacidad para "conmutar" o abrir un camino específico para los datos entre dos puntos.

**Concepto y Características:**

- **Capa del Modelo OSI:** Opera principalmente en la **Capa 2 (Enlace de Datos)**. Algunos avanzados (Layer 3) pueden operar en la capa de Red.    
- **Funcionamiento Inteligente:** El switch aprende las **direcciones MAC** de los dispositivos conectados a cada puerto mediante una tabla llamada CAM (Content Addressable Memory). Cuando recibe un paquete, sabe exactamente a qué puerto debe enviarlo.
- **Dominio de Colisión:** Cada puerto de un switch es un **dominio de colisión independiente**. Esto elimina prácticamente las colisiones de datos.
- **Ancho de Banda dedicado:** Si el switch es de 1 Gbps, cada puerto tiene disponible esa velocidad para su comunicación, sin tener que repartirla con el resto de forma pasiva.
- **Full-Duplex:** Permite enviar y recibir datos simultáneamente sin interferencias.

---

# Cuadro Comparativo: HUB vs. SWITCH

|**Característica**|**HUB (Concentrador)**|**SWITCH (Conmutador)**|
|---|---|---|
|**Capa OSI**|Capa 1 (Física)|Capa 2 (Enlace de Datos)|
|**Inteligencia**|Dispositivo "tonto" (no procesa datos)|Dispositivo inteligente (aprende direcciones MAC)|
|**Gestión de Tráfico**|Difusión (Broadcast) a todos los puertos|Envío selectivo al puerto de destino|
|**Dominios de Colisión**|Uno solo para todo el equipo|Uno por cada puerto|
|**Ancho de Banda**|Compartido entre todos los puertos|Dedicado por puerto|
|**Modo de Transmisión**|Half-Duplex (Unidireccional a la vez)|Full-Duplex (Bidireccional simultáneo)|
|**Seguridad**|Muy baja (tráfico visible para todos)|Alta (tráfico privado entre origen y destino)|
|**Uso actual**|Obsoleto (casi no se fabrican)|Estándar en todas las redes modernas|

**Resumen:** El **Hub** es como un altavoz en una habitación: si alguien habla, todos oyen lo que dice aunque no sea para ellos. El **Switch** es como una central telefónica: establece una línea privada entre quien llama y quien recibe la llamada, permitiendo que muchas conversaciones ocurran al mismo tiempo sin interferirse.