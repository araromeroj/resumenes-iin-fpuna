# Categorías de Ethernet
## Ethernet clásico: capa física

![[Pasted image 20260429092903.png]]

### Características segun la diapositiva
- **Tasa de bits:** $10\text{ Mbps}$
- **Codificación:** Manchester. Ver [[Modulación digital (de bits a señales)#Transmisión en Banda Base]]
- **Cable:** UTP 2 categoría 3 como mínimo y conectores RJ-45
- **Distancia máxima:** $100\text{ m}$
- **Ventaja:** es barato

>[!important] IMPORTANTE
>- Cableado coaxial o UTP con HUBS
>- CSMA/CD 1persistente
>- Algoritmo de retroceso exponencial binario

>[!info] Funcionamiento del CSMA/CD 1-persistente
>-Antes de transmitir, la estación escucha el canal
>	- Si está libre, transmite la trama
>	- Si está ocupado, espera que esté libre y luego transmite
>- Mientras transmite, escucha el canal.
>	- Si se detecta una colisión, interrumpe la transmisión y espera un tiempo aleatorio computado con el **algoritmo exponencial binario**
>- Todas las colisiones ocurren entre el byte 1 y el byte 64 (que es el tamaño de trama mínimo).

>[!info] Funcionamiento del Algoritmo Exponencial Binario
>- División de tiempo en ranuras discretas (de contención) de 64 bytes (mínimo de trama).
>- Tras $i$ colisiones: se escoge entre $0$ y $2^i-1$
>- **Límite del algoritmo:** 1023 ranuras (10 colisiones)
>- **Límite de colisiones:** 16 colisiones
>- No es FIFO !!!

### El HUB Ethernet 10BASE - T

>[!important] IMPORTANTE
>- [I] **HUB:** Es un dispositivo de capa 1 comparable a un repetidor de bits
>- Usa CSMA/CD - estaciones en modo half-duplex
>- Todos los puertos del hub constituyen un "dominio de colisión"
>- Es comparable a un bus de datos

>[!info] Funcionamiento
>Si recibe una transmisión en un Puerto, lo repite en todos los otros puertos
>	Si sucede una colisión, se escucha en todos los puertos


## Fast Ethernet - IEEE 802.3u

>[!important] IMPORTANTE
>- Introducción a la auto-negociación (velocidad y duplexidad)
>- Compatibilidad con 10 Mbps
>- Se mantiene la longitud mínima de trama (64 bytes) a pesar de que la velocidad de transmisión es de 100 Mbps
>- Puede ser conmutado (full dúplex) o con hubs (half dúplex)

| **Nombre**    | **Cable**    | **Maximo segmento** | **Ventajas**                              |
| ------------- | ------------ | ------------------- | ----------------------------------------- |
| 100 Base - T4 | Par trenzado | 100 m               | UTP Cat 3                                 |
| 100 Base - TX | Par trenzado | 100 m               | Full Duplex a 100 Mbps                    |
| 100 Base - FX | Fibra óptica | 2000 m              | Full Duplex a 100 Mbps<br>Carreras largas |
100 Base TX: es el más usado y soportado
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
## Gigabit Ethernet - IEEE 802.3ab (cobre) 802.3z (fibra)

>[!important] IMPORTANTE
>- Soporte para la fibra óptica y cobre
>- Mantiene el formato pero operando principalmente en full-duplex sin colisiones
>- La longitud de trama mínima es de 512 Bytes para mantener la compatibilidad

$$L_{\text{ Trama minima}}=2*\tau *V_{\text{transmisión}}$$ $$L_{\text{ Trama minima}}=2*(d_\text{max}/V_{\text{propagación}}) *V_{\text{transmisión}}$$

## 10 Gigabit Ethernet
>[!important] IMPORTANTE
>- Eliminación definitiva del CSMA/CD
>- Solo funciona en modo full-duplex sobre switch

## Ethernet Conmutado (Switches)
A diferencia de los **hubs** (capa 1), que actúan como repetidores y mantienen un solo dominio de colisión para todos sus puertos, los **switches** (capa 2) crean dominios de colisión independientes por cada puerto.
	Los switches leen los encabezados de las tramas Ethernet. Conociendo las direcciones de origen y destino genera una **trama de conmutación**.
### Modos de Trabajo del Switch:

1. **Cut-through:** El switch lee solo la dirección MAC de destino y empieza a retransmitir la trama de inmediato, sin esperar a recibirla completa. Es el más rápido pero no detecta errores de CRC.    
2. **Free of segments (Fragment-free):** El switch espera a recibir los primeros **64 bytes** (tamaño mínimo) para asegurarse de que no sea un fragmento de colisión antes de retransmitir.
3. **Store and forward:** El switch recibe toda la trama, la almacena, verifica el CRC (control de errores) y luego la transmite en el puerto de destino. Es el método más seguro pero introduce mayor retardo.

### Algoritmos en Ethernet Conmutado
#### DE RETRANSMISIÓN
![[Pasted image 20260429103310.png]]

#### DE APRENDIZAJE
![[Pasted image 20260429103359.png]]



---
# Direccionamiento MAC
- **Formato:** 48 bits (6 bytes)
- **Tipos de direcciones:**
	- [I] **Unicast:** Dirigida a una sola interfaz (bit menos significativo del primer byte = 0)
	- [I] **Multicast:** Dirigida a un grupo (bit menos significativo = 1)
	- [I] **Broadcast:** Dirigida a todos los nodos ($FF:FF:FF:FF:FF:FF$)
		- Los 3 primeros bytes lo define el fabricante
		- Los 3 últimos bytes indican el número de serie
![[Pasted image 20260429102305.png]]
