## Almacenamiento Persistente
Se refiere al transporte físico de datos mediante cintas magnéticas, CD o DVD. Aunque tiene un retardo muy alto, su ancho de banda efectivo puede ser enorme (por ejemplo, el envío de una caja de cintas puede equivaler a una tasa de 70 Gbps).

>[!important] ¡La tasa de datos es meyor que las redes de larga distancia!

## Cables de Par Trenzado
Compuesto por dos hilos de cobre aislados y trenzados helicoidalmente para reducir la interferencia eléctrica.

>[!tip] Utilizado en el sistema telefónico

>[!danger] A distancias mayores necesitan repetidores

### UTP - Unshielded Twisted Pair - Sin blindaje
- Utilizado en líneas telefónicas LAN Ethernet
- Más barato y fácil de instalar
- Sufre más interferencia externa EM

>[!important]
>**Hasta** la Cat.6 son UTP

![[UTP.png|50]]
### FTP - Foiled Twisted Pair - Con hoja metálica
- Hoja metálica que rodea a los cuatro pares de cables
- Protección intermedia
![[FTP.png|50]]

### STP - Shielded Twisted Pair - Con malla metálica
- Malla metálica que reduce la interferencia
- Más caras y difíciles de manejar por ser pesadas y gruesas
![[STP 1.png|50]]
## Categorías de cable de par trenzado
![[cable por categoría.png]]
>[!info]
>Cables de categoría 6 pueden ser UTP y soportar hasta 10Gbps
>Cables nuevos Cat.8 con ancho de banda de 2 HHz usados en Ethernet 25 y 40 Gb con distancias de 30 m

- [I] Full-duplex: Enlaces que pueden utilizarse en ambos sentidos.
- [I] Semi-duplex: Enlaces que pueden usarse en ambos sentidos pero no en simultáneo.
- [I] Simplex: Enlace que solo permite el tráfico en una dirección y sentido.
---
## Cable Coaxial
1. Consta de un hilo de cobre rígido como núcleo
2. Rodeado de un material aislante.
3. El aislante está envuelto por un conductor cilíndrico, en forma de malla trenzada.
4. El conductor está cubierto por una funda protectora de plástico.
![[Cable coaxial.png]]

- Tiene mejor apantallamiento.
- Ancho de banda **amplio**. Mayor ancho de banda que los UTP.
- Abarca distancias más largas a mayor velocidad.
- **Inmunidad al ruido**.
- Permite transmitir muchas conversaciones simultáneamente a través de un solo cable.

>[!info] Cable Twinaxial
>Tiene dos cables trenzados, pero sigue siendo coaxial
>**USO:** Ethernet de 10 GB

### Cable de 50 Ohmios
Se utiliza para la **transmisión digital**.

| Categoria                | Resistencia Eléctrica |
| ------------------------ | --------------------- |
| RG-58 (ethernet delgado) | 50 $\ohm$             |
| RG-11 (ethernet grueso)  | 50 $\ohm$             |

### Cable de 75 Ohmios
Se utiliza para la **transmisión analógica** y la **TV por cable**.

| Categoría | Resistencia Eléctrica |
| --------- | --------------------- |
| RG-59     | 75 $\ohm$             |

---
## Líneas eléctricas o Líneas de potencia (PLC)
Llevan la electricidad a las casas y el cableado de las casas distribuye la electricidad a tomas eléctricas.

- [I] **PLC - Power Line Communications:** Consiste en la utilización del cableado eléctrico doméstico para la comunicación de datos, diseñado para distribuir señales eléctricas. Es una opción conveniente por la ubicuidad de los enchufes, aunque es un medio muy ruidoso y deficiente para altas velocidades.

>[!important] Ventajas
>Conveniente por la ubicuidad de enchufes
>Bueno para distribución eléctrica

>[!danger] Desventajas
>Es muy ruidoso y deficiente para altas velocidades
>Malo para el envío de datos

---
## Fibra óptica
Transmite pulsos de luz a través de una fibra de vidrio ultrafina mediante el principio de reflexión interna total. ==Un pulso de luz indica bit 1 y la ausencia de luz indica bit 0==. Es inmune a interferencias electromagnéticas porque el medio de transmisión es vidrio y utiliza luz en lugar de señales eléctricas.
- [I] **Dispersión cromática:** El fenómeno que provoca que los pulsos de luz se extiendan en longitud a medida que se propagan por la fibra.
Se compone de:
1. Fuente de luz ([[Medios Guiados de Transmisión#Tipos de fuentes de luz|LED o ILD]])
2. Medio de transmisión (vidrio)
3. Detector
- [I] **Fotodiodo:** dispositivo que convierte la señal del dominio óptico al eléctrico en el extremo receptor.

| **Ventajas**                                                 | **Desventajas**              |
| ------------------------------------------------------------ | ---------------------------- |
| Es **inmune a interferencias electromagnéticas** (aislación) | Unidireccional (**simplex**) |
| Ofrece ancho de banda **extremadamente** altos.              | Frágil                       |
| Baja atenuación                                              | Costo elevado                |
| Espaciado entre repetidores                                  | Tecnología muy específica    |

![[Fibra óptica dibujo.png|400]]

>[!important] No olvidar!
>**Convertir una relación de potencia a escala logarítmica de decibelios**
> $$10*log_{10}(\text{Factor Lineal})=\text{dB}$$
### Tipos

| **Monomodo**                                                                                                             | **Multimodo**                                                                             |
| ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| La fibra actúa como guía de ondas y la luz sólo puede propagarse en línea recta, **sin rebotar**, se llama **monomodo**. | Si cada rayo tiene un modo diferente se llama **multimodo**.                              |
| Núcleo delgado<br>Para largas distancias hasta 100 km<br>Caras<br>Mayor ancho de banda                                   | Núcleo grueso<br>Para distancias cortas hasta 15 Km<br>Baratas<br>Ancho de banda limitado |
### Tipos de fuentes de luz
- [I] LED: Diodos emisores de luz
- [I] ILD: Laser semiconductor

| LED                                     | LID                                          |
| --------------------------------------- | -------------------------------------------- |
| Velocidad **BAJA**                      | Velocidad **ALTA**                           |
| Tipo **MULTIMODO**                      | Tipo **MONOMODO O MULTIMODO**                |
| Distancia **CORTA**                     | Distancia **LARGA**                          |
| Vida **LARGA**                          | Vida **CORTA**                               |
| Sensibilidad a la temperatura **MENOR** | Sensibilidad a la temperatura **SUSTANCIAL** |
| Costo **BAJO**                          | Costo **ALTO**                               |
### Métodos de multiplexación de señales en fibra óptica
- [I] **WDM (Wavelength Division Multiplexing):** multiplexa múltiples señales en una sola fibra óptica usando diferentes longitudes de onda.
---
# Enlaces relacionados
- [[2. Capa Física]]
- Siguiente cap: [[Medios no guiados de transmisión]]