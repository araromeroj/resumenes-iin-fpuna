
- [I] **ARQ:** Es un mecanismo de control de errores utilizado para garantizar la entrega fiable de datos a través de canales de comunicación, especialmente en canales ruidosos donde las tramas pueden dañarse o perderse.
- [*] **ARQ - Automatic Repeat reQuest:** Solicitud de repetición automática.

>[!info] Funcionamiento
>Consiste fundamentalmente en que el receptor confirma la llegada de los datos y el emisor retransmite la información si no recibe dicha confirmación en un tiempo determinado.

## Elementos fundamentales del ARQ
Para que este sistema funcione correctamente, se basa en tres componentes clave:
1. **Acuses de recibo (ACK):** El receptor debe enviar una trama de control especial al emisor confirmando que ha recibido una trama correctamente.
2. **Temporizadores (Timers):** El emisor inicia un temporizador tras enviar cada trama. Si el temporizador expira antes de recibir el ACK, el emisor asume que la trama (o su confirmación) se perdió y procede a retransmitirla.
3. **Numeración de secuencias:** Tanto las tramas como los ACKs deben estar numerados. Esto permite al receptor distinguir si una trama entrante es una información nueva o una retransmisión de una trama que ya había aceptado previamente (lo cual ocurre si el ACK original se perdió en el camino)

>[!example] EJEMPLO
>- **Concepto desde cero:** Los cables no son perfectos; hay interferencias y los paquetes a veces se pierden en el camino (se "caen").
>- Para solucionar esto, existe el **ARQ (Reenvío Automático)**.
>- _Ejemplo:_ Yo te envío el paquete número 1. Empiezo a contar en mi reloj (uso un "Timer"). Si el tiempo se agota y tú no me has enviado el "ACK" confirmando que llegó, yo asumo que se perdió y **te lo vuelvo a enviar**.
>- Por esto es obligatorio **numerar los paquetes**, porque de lo contrario, si me retraso respondiendo, podrías enviarme el mismo paquete dos veces y yo pensaría que es un paquete nuevo.