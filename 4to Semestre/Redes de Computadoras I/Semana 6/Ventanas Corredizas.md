- [I] **Ventanas Corredizas - pipelining:** son una clase de protocolos de comunicación bidireccional que permiten un control eficiente del flujo de datos y del error en la capa de enlace y en la de transporte. Este concepto permite que el emisor transmita significativamente el rendimiento del canal.
	- tiene tramas **numeradas**
	- para confirmar tramas utiliza **superposición en la trama de datos** y **trama de control ACK**
	- también puede usar confirmación negativa o NAK

- [*] **NAK - Negative Acknowledgment:** confirmación negativa
- [*] **ACK - Acknowledgement:** reconocimiento o acuse de recibo
- [*] **NIC - Network Interface Card:** Tarjeta de interfaz de Red
- [*] **ARQ - Automatic Repeat reQuest:** Solicitud de repetición automática

- [I] **Buffer:** espacio en memoria temporal, para almacenar datos mientras se transfieren de un lugar a otro, previene interrupciones en procesos al acumular datos antes de procesarlos.

>[!info] Funcionamiento
>- Tanto emisor como receptor mantienen un conjunto de números de secuencia que representan las unidades de datos que pueden procesar en un momento dado.
>- **Ventana de envío (Emisor):** representa el grupo de números de secuencia de las tramas que el emisor tiene permitido enviar sin esperar un ACK. Cuando un emisor recibe un paquete de la capa de red (una nueva trama), se le asigna el siguiente número de secuencia y el borde **superior** de la ventana avanza. Al recibir el ACK, el borde **inferior** avanza, liberando espacio en buffers. El tamaño es variable.
>- **Ventana de Recepción (Receptor):** es el conjunto de números de secuencia de las tramas que el receptor está dispuesto a aceptar (de forma ordenada). Si llega una trama con un número de secuencia dentro de esta ventana, se coloca el buffer; si está fuera de la ventana, se descarta. Cuando se recibe la trama esperada (borde inferior), esta se entrega a la capa superior y la ventana rota o avanza. El tamaño es fijo.
>- Buffers y Retransmisión: el emisor debe mantener copias de todas las tramas enviadas que aún o han sido confirmadas por si se pierden o dañan y requieren retransmisión. De igual modo, el receptor necesita espacio en el buffer para gestionar las llegadas.

>[!warning] Las ventanas de emisión y recepción no son necesariamente del mismo tamaño.

	En los canales ruidosos, ARQ añade un control de errores
	- El receptor confirma la recepción del ACK.
	- El emisor usa un timer y reenvía las tramas si no recibe la info.
	Las tramas y ACK's deben estar **numeradas** para distinguir las retransmmisiones de tramas nuevas. Y para protocolos SAW, 2 números son suficientes (1 bit en el campo de secuencia/ACK)
## Características principales

- [I] **Piggybancking (superposición):** técnica que consiste en retrasar temporalmente el envío de ACK's para adjuntarlos a la siguiente trama de datos saliente, optimizando el uso del ancho de banda del canal inverso.
- [I] **Números de Secuencia:** cada trama enviada contiene un número de secuencia que va desde 0 hasta un máximo ($2^n-1$ para un campo de $n$ bits). Estos son esenciales para que el receptor distinga entre tramas nuevas y retransmisiones.
- [I] **Pipeling (canalización):** es la técnica de mantener varias tramas "en vuelo" simultáneamente a través de un canal. Esto es vital en enlaces donde el retardo de propagación es largo, evitando que el emisor se bloquee esperando respuestas.

El pipeling depende del bandwidth-delay (BD):
$$B \text{ [tramas/segundo]}=\frac{\text{tasa de datos}}{\text{longitud de trama}} [\frac{\text{bits/segundo}}{\text{bits}}]$$
$$D_p\text{ [segundos]}= \text{retardo de propagación}$$
>[!tip] Propiedades del pipelining
>- $W \geq{2BD_p}+1$ para asegurar utilización alta del enlace $(100\%)$
>- $\text{Eficiencia o utilización del enlace}\leq{\frac{W}{1+2BD_p}}$
### Ventajas y Desventajas

| **Ventajas**                                                                          | **Desventajas**                                                                             |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Mejor uso del ancho de banda del canal<br>Menos carga de procesamiento en el receptor | Se debe determinar el tiempo que la capa de enlace espera por un paquete para enviar el ACK |

---
# Enlaces relacionados
- Siguiente nota: [[Funcionamiento de las Ventanas Corredizas]]
- [[Tipos de Ventanas]]