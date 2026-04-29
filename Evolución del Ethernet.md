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

#### Sub-capa MAC
Usa CSMA/CD 1-persistente

>[!info] Funcionamiento del CSMA/CD 1-persistente
>- Antes de transmitir, la estación escucha el canal.
>- Si está libre, transmite la trama.
>- Si está ocupado, espera que esté libre y luego transmite.
>- Mientras transmite, escucha el canal. Si detecta una colisión, interrumpe la transmisión y espera un tiempo aleatorio computado con el algoritmo exponencial binario.
>- Todas las colisiones ocurren entre el byte 1 y el byte 64.
#### Algoritmo Exponencial Binario

>[!info] Funcionamiento
>- División de tiempo en ranuras discretas de 64 bytes.
>- Tras $i$ colisiones: se escoge entre $0$ y $2^i-1$ ranuras.
>- **Límite del Algoritmo:** 1023 ranuras (10 colisiones).
>- **Límites de Colisiones:** 16
>- El algoritmo es injusto: No es FIFO


## Fast Ethernet (100 Mbps)

Llegó en 1995 como el estándar **802.3u**. El objetivo era ser 10 veces más rápido manteniendo la compatibilidad con las tramas del Ethernet original.

- **Innovación:** Introdujo la **Auto-negociación**. Este protocolo permite que dos dispositivos "hablen" y decidan la mejor velocidad (10 o 100 Mbps) y el modo (Half o Full Duplex).
    
- **Cableado:** Se estandarizó el uso de **UTP Categoría 5** y conectores RJ-45.
    
- **Dato Técnico:** El tiempo de bit se redujo de $100 ns$ a $10 ns$.

## Gigabit Ethernet (1 Gbps)

Estandarizado como **802.3z** (fibra) y **802.3ab** (cobre). Aquí la industria empezó a abandonar los Hubs masivamente.

- **Conmutación:** Aunque soporta CSMA/CD para ser compatible, casi todas las instalaciones son **Full-Duplex** conectadas a un Switch.
    
- **Eficiencia:** En modo Full-Duplex, no hay colisiones, por lo que el límite de distancia ya no depende del tiempo de propagación de la señal, sino de las capacidades físicas del cable.
    
- **Manejo de Trama:** Introduce el "Carrier Extension" (extensión de portadora) para mantener el tamaño de trama de 64 bytes en modo Half-Duplex, aunque hoy en día es casi obsoleto.

## 10-Gigabit Ethernet (10 Gbps) y Superiores

El estándar **802.3ae** marcó un antes y un después.

- **Adiós al CSMA/CD:** Este estándar **no soporta CSMA/CD**. Solo funciona en modo Full-Duplex.
    
- **Adiós a los Hubs:** Solo puede conectarse mediante Switches.
    
- **Uso:** Principalmente para centros de datos y _backbones_ (núcleos) de redes empresariales.
    
- **Evolución Continua:** Ya existen estándares de **40 Gbps, 100 Gbps y hasta 400 Gbps**, utilizados para mover volúmenes masivos de datos en la nube.

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
