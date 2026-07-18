## Ethernet Clásico (10 Mbps)

Fue el inicio de todo bajo el estándar **IEEE 802.3**. Su característica principal era el uso de un medio compartido (cable coaxial o Hubs).

- **Mecanismo:** Utiliza el algoritmo **CSMA/CD** (Detección de Portadora y Detección de Colisiones).    
- **Restricción Crítica:** Para que la detección de colisiones funcione, la trama debe ser lo suficientemente larga para que el emisor siga transmitiendo cuando el "eco" de la colisión regrese. Por eso, el tamaño mínimo de trama es de **64 bytes**.
- **Topología:** Originalmente en bus (cable grueso/fino), luego evolucionó a estrella usando **Hubs** (Capa 1).
- **Características:** Usa codificación Manchester, cable UTP 2 Cat 3, conectores RJ-45, distancia máxima de $100 \text{ m}$

### Ethernet 10BASE-T

>[!summary] HUB
>- [I] **HUB:** es un dispositivo repetidor de bits
>- Es comparable a un bus de datos.

>[!info] Funcionamiento
>- Si recibe una transmisión en un Puerto, lo repite en todos los otros puertos.
>- Si sucede una colisión, se escucha en todos los puertos.
>- El HUB es un dispositivo de "capa 1" comparable a un repetidor de bits.

- **Características:** usa CSMA/CD, estaciones half duplex, todos los puertos del hub constituyen un "dominio de colisión".
#### Sub capa MAC

>[!info] Funcionamiento del CSMA/CD 1-persistente
>- Antes de transmitir, la estación escucha el canal
>	- Si está libre, transmite la trama
>	- Si está ocupado, espera que esté libre y luego transmite
>- Mientras transmite, escucha el canal.
>	- Si se detecta una colisión, interrumpe la transmisión y espera un tiempo aleatorio computado con el **algoritmo exponencial binario**
>- Todas las colisiones ocurren entre el byte 1 y el byte 64 (que es el tamaño de trama mínimo).

#### Algoritmo Exponencial Binario (Binary Exponential Backoff)
- [*] **Binary Exponential Backoff:** Algoritmo de Retroceso Exponencial Binario

Es el corazón del protocolo CSMA/CD usado en Ethernet de half-dúplex. Su función es decidir cuánto tiempo debe esperar una estación después de que ocurre una colisión antes de intentar transmitir de nuevo.

>[!info] Funcionamiento del Algoritmo Exponencial Binario
>1. **Detección:** Si dos estación es transmiten al mismo tiempo, ocurre una colisión.
>2. **Intento $k$:** Se registra el número de colisiones consecutivas para ese frame (máximo 16).
>3. **Rango de espera:** La estación elige un número aleatorio $r$ dentro de ese rango de $[0, 2^k-1]$.
>4. **Tiempo de espera:** El tiempo de espera real es de $r*\text{SlotTime}$ (512 bits en Ethernet)
>5. **Crecimiento:** El rango de espera se duplica tras cada colisión por ser exponencial, lo que reduce la probabilidad de que las mismas estaciones vuelvan a chocar.

>[!tip] Características
>- División de tiempo en ranuras discretas (de contención) de 64 bytes (mínimo de trama).
>- Tras $i$ colisiones: se escoge entre $0$ y $2^i-1$
>- **Límite del algoritmo:** 1023 ranuras (10 colisiones)
>- **Límite de colisiones:** 16 colisiones
>- No es FIFO !!!

[[Datos técnicos y estructura de trama]]

### Árbol Binario - Resolución de Colisiones

Aunque el _Backoff_ es el estándar comercial, el **Algoritmo de Árbol** es una forma determinista de resolver colisiones dividiendo las estaciones en grupos.

>[!info] Funcionamiento:
>1. **División:** Cuando hay una colisión, todas las estaciones involucradas se dividen en dos grupos (un "árbol" con rama 0 y rama 1).
>2. **Prioridad:** Solo las estaciones en la rama 0 (izquierda) intentan transmitir.
>3. **Recursión:**
>	- Si hay éxito, luego le toca a la rama 1.
>	- Si hay otra colisión en la rama 0, ese grupo se vuelve a dividir en dos sub-ramas.
>4. **Finalización:** El proceso continúa hasta que todas las estaciones han transmitido con éxito siguiendo un recorrido en orden (in-order traversal) del árbol.  

![[Pasted image 20260503172819.png]]

---
## Fast Ethernet (100 Mbps)

Llegó en 1995 como el estándar **802.3u**. El objetivo era ser 10 veces más rápido manteniendo la compatibilidad con las tramas del Ethernet original.

- **Innovación:** Introdujo la **Auto-negociación**. Este protocolo permite que dos dispositivos "hablen" y decidan la mejor velocidad (10 o 100 Mbps) y el modo (Half o Full Duplex).
- **Cableado:** Se estandarizó el uso de **UTP Categoría 5** y conectores RJ-45.
- **Dato Técnico:** El tiempo de bit se redujo de $100 ns$ a $10 ns$.
- Se mantiene la longitud mínima de trama (64 bytes) a pesar de que la velocidad de transmisión es de 100 Mbps.
- Puede ser conmutado (full dúplex) o con hubs (half dúplex).

| **Nombre**    | **Cable**    | **Maximo segmento** | **Ventajas**                              |
| ------------- | ------------ | ------------------- | ----------------------------------------- |
| 100 Base - T4 | Par trenzado | 100 m               | UTP Cat 3                                 |
| 100 Base - TX | Par trenzado | 100 m               | Full Duplex a 100 Mbps                    |
| 100 Base - FX | Fibra óptica | 2000 m              | Full Duplex a 100 Mbps<br>Carreras largas |
100 Base TX: 
	- Es el más usado y soportado
	- Usa dos pares UTP Cat 5
	- **Codificación:** 4B/5B a 125 MHz
	- Full dúplex

100 Base T4:
	- Usa cuatro pares UTP Cat 3
		Uno hacia el hub, uno hacia el host y 2 configurables
	- **Codificación:** 8B/6T en tres pares - señales terna
	- Full dúplex

100 Base - FX:
	- Fibra multimodo
	- Distancia máxima de 400 metros (en half dúplex) y 2000 metros (en full dúplex)
	- **Codificación:** 4B/5B y NRZI

==TODOS COMPATIBLES CON ETHERNET 10 Mbps AUTONEGOCIACIÓN==

## Gigabit Ethernet (1 Gbps)

Estandarizado como **802.3z** (fibra) y **802.3ab** (cobre). Aquí la industria empezó a abandonar los Hubs masivamente.
- IEEE 802.3ab: 1000Base-T Gigabit Ethernet
	- Usa 4 pares cat 5e (125 MHz)
	- Full dúplex dual
	- Permite uso de hubs (CSMA/CD) y conmutadores.
- [*] **FDX:** Full dúplex dual

![[Pasted image 20260429185030.png]]

- **Conmutación:** Aunque soporta CSMA/CD para ser compatible, casi todas las instalaciones son **Full-Duplex** conectadas a un Switch.
    
- **Eficiencia:** En modo Full-Duplex, no hay colisiones, por lo que el límite de distancia ya no depende del tiempo de propagación de la señal, sino de las capacidades físicas del cable.
    
- **Manejo de Trama:** Introduce el "Carrier Extension" (extensión de portadora) para mantener el tamaño de trama de 64 bytes en modo Half-Duplex, aunque hoy en día es casi obsoleto.

$$L_{\text{ Trama minima}}=2*\tau *V_{\text{transmisión}}$$ $$L_{\text{ Trama minima}}=2*(d_\text{max}/V_{\text{propagación}}) *V_{\text{transmisión}}$$
==Se requiere la misma longitud de trama mínima para mantener la compatibilidad==

## 10-Gigabit Ethernet (10 Gbps) y Superiores

El estándar **802.3ae** marcó un antes y un después.

![[Pasted image 20260429185231.png]]

- **Adiós al CSMA/CD:** Este estándar **no soporta CSMA/CD**. Solo funciona en modo Full-Duplex.
    
- **Adiós a los Hubs:** Solo puede conectarse mediante Switches.
    
- **Uso:** Principalmente para centros de datos y _backbones_ (núcleos) de redes empresariales.
    
- **Evolución Continua:** Ya existen estándares de **40 Gbps, 100 Gbps y hasta 400 Gbps**, utilizados para mover volúmenes masivos de datos en la nube.

IEEE 802.3z:
	1000Base-SX: Con LEDs (más barato)
	1000Base-LX: ILDs (más caro)

### 1000 Base-TX
- **1000Base-TX:** 2 pares de UTP cat 6 - TIA/EIA 854 - Estándar distinto al 1000Base-T
- **Jumbo frames:** tramas de 9000 bytes (no estandarizado por IEEE)

![[Pasted image 20260429190422.png]]

---
# Diferencias Clave

1. **El Medio:** Pasamos de un cable compartido donde todos "gritaban" al mismo tiempo (Hub), a canales privados donde cada uno tiene su propio carril (Switch).
    
2. **El Algoritmo:** CSMA/CD era vital en 10 Mbps, es opcional en 1 Gbps y está prohibido (eliminado) en 10 Gbps.
    
3. **La Distancia:** En Ethernet clásico, la red no podía ser muy grande porque el emisor debía detectar la colisión a tiempo. En las versiones modernas Full-Duplex, la fibra óptica permite distancias de kilómetros.

### Cuadro Comparativo de Estándares Ethernet

|**Característica**|**Ethernet Clásico**|**Fast Ethernet**|**Gigabit Ethernet**|**10-Gigabit Ethernet**|
|---|---|---|---|---|
|**Estándar IEEE**|802.3|802.3u|802.3z / 802.3ab|802.3ae|
|**Velocidad**|10 Mbps|100 Mbps|1,000 Mbps|10,000 Mbps|
|**Protocolo MAC**|CSMA/CD|CSMA/CD / Full-Duplex|CSMA/CD (raro) / Full-Duplex|**Solo Full-Duplex**|
|**Medio Típico**|Coaxial / UTP Cat 3|UTP Cat 5|UTP Cat 5e/6 / Fibra|Fibra / UTP Cat 6a/7|
|**Dispositivo Central**|Hub (principalmente)|Hub o Switch|Switch|**Solo Switch**|
|**Auto-negociación**|No disponible|Introducida|Obligatoria/Estándar|Estándar|

---
# Autonegociación

La **autonegociación** es un mecanismo de la capa física (Capa 1) introducido originalmente con el estándar **Fast Ethernet (802.3u)** que permite que dos dispositivos conectados por un cable de red "hablen" y se pongan de acuerdo sobre la mejor velocidad y modo de transmisión que ambos soportan.
## 1. ¿Cómo funciona? (Los pulsos FLP)

La autonegociación no utiliza tramas de datos complejas para comunicarse, ya que en ese punto la conexión aún no está establecida. En su lugar, utiliza **Pulsos de Enlace Rápido** (FLP - _Fast Link Pulses_).

- Los dispositivos envían una ráfaga de pulsos que codifican sus capacidades.    
- Estos pulsos son compatibles con los "pulsos de integridad de enlace" del Ethernet antiguo (10 Mbps), por lo que un dispositivo moderno no "romperá" a uno viejo al intentar negociar.

## 2. ¿Qué es lo que negocian?

Los dispositivos comparan sus listas de capacidades y eligen el **máximo común denominador** siguiendo esta jerarquía de prioridad (de mejor a peor):

1. **1000Base-T** (Gigabit) Full Duplex
2. **1000Base-T** (Gigabit) Half Duplex
3. **100Base-TX** (Fast Ethernet) Full Duplex
4. **100Base-TX** (Fast Ethernet) Half Duplex
5. **10Base-T** (Ethernet clásico) Full Duplex
6. **10Base-T** (Ethernet clásico) Half Duplex

- Permite ajustar el protocolo a utilizarse de forma automática (puertos 10/100/1000).
- Al conectarse los equipos negocian la comunicación siguiendo una prioridad
- Sólo se utiliza en puertos con cable UTP. En la fibra lo único negociable es el modo dúplex.
- La Autonegociación puede no ser posible entre equipos de marcas diferentes
- La autonegociación es opcional, puede estar o no.