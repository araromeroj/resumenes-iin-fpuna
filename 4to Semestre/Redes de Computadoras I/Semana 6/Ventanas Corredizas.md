- [I] **Ventanas Corredizas:** son una clase de protocolos de comunicación bidireccional que permiten un control eficiente del flujo de datos y del error en la capa de enlace y en la de transporte. Este concepto permite que el emisor transmita significativamente el rendimiento del canal.
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
# Tipos de ventanas corredizas
- [*] **Stop and wait:** parada y espera
- [*] **Go back N:** retroceso N
- [*] **Selective Repeat:** repetición selectiva

## Stop and wait (Parada y Espera) $(W=1)$

- [I] **Stop and Wait:** Es el control de flujo y errores en la capa de enlace de datos, es un protocolo de ventana corrediza con **tamaño de ventana igual a 1** $(W=1)$. Utiliza el número de secuencia de 1 bit, alternando entre 0 y 1 para distinguir entre una trama nueva y una retransmisión.

>[!info] Funcionamiento de SAW
>El emisor transmite una única trama y luego debe detenerse y esperar una confirmación del receptor antes de poder enviar el siguiente elemento de datos.

### Proceso del emisor
1. Obtiene un paquete de la capa de red, construye una trama y la envía a través de la capa física.
2. Inicia un temporizador o RTO para recuperarse en caso de pérdida de la trama o de su ACK.
3. Queda bloqueado esperando un evento. Si recibe un ACK válido, detiene el timer, avanza el número de secuencia y busca el siguiente paquete.
4. Si el timer expira antes de recibir el ACK, el emisor retransmite la misma trama almacenada en su búffer.

### Proceso del receptor
1. Espera la llegada de una trama. Al recibirla, comprueba si el número de secuencia es el esperado.
2. Si es la correcta, entrega los datos a la capa de red y actualiza el número de secuencia que espera a continuación.
3. Envía una trama de ACK de vuelta al emisor para darle permiso de continuar.

## Go back N (Retroceso N) $(W>1)$

- [I] **Go back N:** Es una técnica de ventana corrediza diseñada para gestionar la transmisión de datos de forma eficiente a través de canales que pueden presentar errores, permitiendo que el emisor transmita múltiples tramas antes de recibir una confirmación.
$$W>1, W=2^k-1$$
- [*] **MAX_SEQ - Maximum Sequence Number:** Número máximo de secuencia

>[!tip] La ventana de envío $(W)$ es como máximo $(2^k-1)$

>[!info] Funcionamiento
>Permite el pipelining (mantiene varias tramas en vuelo simultáneamente) para no desperdiciar la capacidad de enlace.

### En el emisor
El emisor mantiene una ventana de envío que contiene números de secuencia de tramas que tiene permitido transmitir sin esperar a un ACK.
Si el emisor alcanza un límite de su ventana y no recibe ACK de la trama más antigua, se bloquea.
Al expirar un timer para una trama específica, el emisor retrocede y vuelve a transmitir esa trama y todas las siguientes que ya habían sido enviadas pero no confirmadas.

### En el receptor
El receptor tiene una ventana de recepción de tamaño 1, lo que significa que solo acepta tramas que lleguen estrictamente en el orden correcto.
Si llega una trama con un error o fuera de secuencia, el receptor la descarta, así como a todas las tramas que le sigan, sin enviar confirmación por ellas.

>[!example] Ejemplo
>Si el receptor recibe la trama 3 pero esperaba la trama 2, hasta que no exista el ACK de la trama 2 entonces el receptor descartará la 3 y todas las que le siguen, sin enviar confirmación por ellas.

