- [I] **Ventanas Corredizas:** son una clase de protocolos de comunicación bidireccional que permiten un control eficiente del flujo de datos y del error en la capa de enlace y en la de transporte. Este concepto permite que el emisor transmita significativamente el rendimiento del canal.

>[!info] Funcionamiento
>- Tanto emisor como receptor mantienen un conjunto de números de secuencia que representan las unidades de datos que pueden procesar en un momento dado.
>- Ventana de envío (Emisor): representa el grupo de números de secuencia que las tramas que el emisor tiene permitido enviar sin esperar un ACK.

- [I] **Piggybancking (superposición):** técnica que consiste en retrasar temporalmente el envío de ACK's para adjuntarlos a la siguiente trama de datos saliente, optimizando el uso del ancho de banda del canal inverso.
- [I] **Números de Secuencia:** cada trama enviada contiene un número de secuencia que va desde 0 hasta un máximo ($2^n-1$ para un campo de $n$ bits). Estos son esenciales para que el receptor distinga entre tramas nuevas y retransmisiones.
- [I] **Pipeling (canalización):** es la técnica de mantener varias tramas "en vuelo" simultáneamente a través de un canal. Esto es vital en enlaces donde el retardo de propagación es largo, evitando que el emisor se bloquee esperando respuestas.

>[!important] Concepto de Piggybacking
>Se intercalan tramas de datos y tramas de control ACK en el mismo enlace, el receptor debe confirmar la recepción (ACK).
>Se puede retardar temporalmente los envíos de ACK's de manera a incluirlos en la siguiente trama de datos (en el campo de ACK en el encabezado).

### Ventajas y Desventajas

| **Ventajas**                                                                          | **Desventajas**                                                                             |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Mejor uso del ancho de banda del canal<br>Menos carga de procesamiento en el receptor | Se debe determinar el tiempo que la capa de enlace espera por un paquete para enviar el ACK |

## Canales ruidosos

- [*] **NIC - Network Interface Card:** Tarjeta de interfaz de Red
- [*] **ARQ - Automatic Repeat reQuest:** Solicitud de repetición automática
- [*] **ACK - Acknowledgement:** reconocimiento o acuse de recibo
