- [I] **Piggybacking:** es una técnica utilizada en la transmisión bidireccional de datos que consiste en **adjuntar el acuse de recibo (ACK) de una trama recibida a la siguiente trama de datos que se envíe** en sentido contrario.
	En lugar de enviar una trama de control dedicada exclusivamente para confirmar la recepción, el receptor espera un breve periodo de tiempo hasta que su propia capa de red le entregue un paquete para transmitir. En ese momento, inserta la confirmación en un campo específico del encabezado de la trama de datos saliente.

>[!info] Funcionamiento
>El receptor demora temporalmente el envío del ACK con la esperanza de poder "engancharlo" a una trama de datos que viaje hacia el emisor original. Si no hay datos para enviar tras un periodo determinado, se termina enviando una trama de control ACK independiente para evitar que el emisor original agote su tiempo de espera y retransmita innecesariamente.


| **Ventajas**                 | **Desventajas** |
| ---------------------------- | --------------- |
| Mejor uso de ancho de banda  |                 |
| Menor carga de procesamiento |                 |

## Ventajas
- Mejor uso del ancho de banda
- Menor carga de procesamiento
## Desventajas
- **Gestión del tiempo:** Es difícil determinar exactamente cuánto tiempo debe esperar la capa de enlace por un paquete antes de enviar un ACK por separado. Si la espera es superior al temporizador del emisor, este retransmitirá la trama, invalidando el propósito de la técnica.
- **Complejidad:** Requiere un esquema _ad hoc_ (como esperar un número fijo de milisegundos) para equilibrar la eficiencia y la prontitud de las confirmaciones.
# EJEMPLO: 
- **Piggybacking (Montarse a cuestas):** Enviar un paquete que _solamente_ diga "ACK" desperdicia el espacio de tu internet. Lo que hacen las computadoras es **retrasar** el ACK un poquito de tiempo, y lo "pegan" o "montan" dentro del próximo paquete de datos normal que tu amigo te iba a enviar de todas formas.
- Es como si recibes una carta y, en lugar de gastar en un sello postal solo para decir "me llegó", esperas a escribirle otra carta a esa persona y le agregas una nota al pie diciendo "por cierto, me llegó tu carta anterior". Esto mejora el uso de tu internet, aunque es difícil calcular cuánto tiempo exacto hay que esperar.