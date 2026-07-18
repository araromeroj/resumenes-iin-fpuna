
![[Pasted image 20260524233024.png]]

>[!note] Explique
>**TXOP:** Es un método de calidad de servicio en las redes 802.11, sirve para que estaciones lentas no saturen o perjudiquen mucho a estaciones rápidas.
>**CSMA/CD:** Es acceso múltiple con detección de portadora y detección de colisiones, en los métodos se reconoce si el canal presenta alguna colisión y se escucha en todas las estaciones para poder transmitir.
>**ICMP:** Sirve para control y notificación de errores, el ICMP se envía al IP que encaptula el mensaje y luego transmite el datagrama. Hay 8 tipos de mensajes ICMP
>- Problema de parámetro, destino inalcanzable, eco y eco request, solicitud y respuesta con marca de tiempo, redireccionamiento, origen extinto, solicitud de router, tiempo excedido.
>
>**APSD:** Es una técnica o mecanismo de ahorro de energía utilizado en el 802.11 (Automatic Power Save Delivery) Consiste en que se envían las tramas al cliente automáticamente después de que este haya enviado el mensaje durante periodos de servicio programados o no programados.
>**PAT:** Port Adress Translation es un protocolo que relaciona direcciones IP públicas a IP privadas de modo que si dos estaciones quieren acceder a una misma red y tienen el mismo puerto, en el router con el PAT se le asignan diferentes puertos a ambos hosts y se utiliza una tabla de NAT para el seguimiento.

![[Pasted image 20260524233034.png]]

- Memoria **RAM**: Guarda la tabla de enrutamiento, la configuración actual del router, colas de paquetes y el SO en ejecución.
- Memoria **NVRAM**: Guarda la configuración de inicio que se copia en la memoria de trabajo durante el inicio del equipo. Es una memoria ram de poca capacidad.
- Memoria **Flash**: Guarda la imagen del SO
- Memoria **ROM**: Guarda el programa de arranque y el software básico del SO, las pruebas de inicio y rutinas de diagnóstico de hardware.

![[Pasted image 20260524233524.png]]

1. Escucha el medio para saber si alguien más está transmitiendo.
2. Si el canal está ocupado, espera que se libere.
3. Si se libera, espera el tiempo obligatorio DIFS.
4. Si luego del DIFS el canal sigue libre, entonces se elige un tiempo aleatorio dentro de la ventana de contención. $[1, CW_{min}]$
5. Empieza la cuenta regresiva, el contador de backoff disminuye en 1 por cada ranura de tiempo que el canal esté libre.
6. Si otra estación empieza a transmitir antes de que el contador llegue a cero, el contador se congela hasta que vuelva a estar libre y pase otro periodo DIFS.
7. Se transmite cuando finalmente llega a cero.
8. Si la estacón transmite pero no recibe el ACK, asume que hubo colisión o interferencia, entonces el número aleatorio se vuelve a elegir pero esta vez con el doble de rango que el anterior. $[1, 2CW_{min}]$
No se usa el algoritmo de backoff cuando el medio está inactivo a la llegada de una nueva trama. Si el canal ha estado libre durante un tiempo igual o mayor al DIFS se transmite la trama por el medio inmediatamente.

![[Pasted image 20260524234521.png]]

1. Se recibe la trama en el puerto "x".
2. Se lee la dirección MAC de destino
	Si la MAC es de broadcast se reenvia la trama por todos los puertos menos en el destino.
2. ¿Está la dirección de destino en la tabla CAM?
	Si la dirección de destino no está en la CAM, se reenvía la trama por todos los puertos menos en el de destino.
3. ¿Es el puerto por donde vino el mismo que el puerto de salida de la CAM?
	Si es así, se termina el forwarding
4. Si no está, se envía la trama por el puerto de salida indicado "x".

![[Pasted image 20260525114816.png]]

1. Preámbulo (7 bytes): Para indicar que es la trama de ethernet.
2. SFD (1 byte): Indica el inicio de la trama
3. Origen (6 bytes): Dirección de origen
4. Destino (6 bytes): Dirección de destino
5. X'8100: indicador de protocolo VLAN
6. TAG (16 bytes): tiene la prioridad, el indicador de vlan y el CPI que se usa en token ring.
7. Ethertype / Longitud (2 bytes): indica la longitud de la trama o el protocolo de ethernet a utilizarse.
8. Data (0 - 1500 bytes): son los datos o la carga útil de la trama.
9. Pad (0 - 46 bytes): es un campo que se utiliza para rellenar y llegar a los 64 bytes de trama mínima.
10. CRC (4 bytes): indicado para la detección y corrección de errores.

![[Pasted image 20260525001010.png]]

- Repetición selectiva -> $2^{k-1}$ que sería la mitad de los bits de la ventana corrediza.
- $k=3 \text{ bits}$
- Utiliza *Superposición o Piggybacking* que tiene la siguiente fórmula $E = \frac{W*t_t}{2t_t+2t_p}$
- Longitud del cable $C = 6 \text{ km} = 6000 \text{ m}$ 
- Tasa de las estaciones $V_t = 50 \text{ Mbps}$
$$80\%\leq \frac{2^{3-1}*t_t}{2t_t+2*\frac{6000}{3*10^8}}$$
$$t_t \geq 13.333 \dots \mu\text{s} $$
$$L \geq t_t*V_t$$
$$L \geq 13.333*10^{-6} *50*10^6$$
$$L = 500 \text{ bytes}$$

![[Pasted image 20260525114105.png]]
Protocolos de árbol de expansión:
Los protocolos de arbol de expansión sirven para determinar caminos entre dos nodos pero sin entrar en bucles.
- **STP - Spanning Tree Protocol (802.11d):** Es el protocolo original en el que el switch elige y bloquea los cables redundantes, en el caso de que el cable principal elegido se corte el stp sabe otro camino por el cual seguir que era el otro inactivo.
	- Evita bucles pero muy lento.
- **RSTP - Rapid Spanning Tree (802.11w):** Es el protocolo utilizado por defecto, hace lo mismo que el stp pero utiliza estados de puerto más inteligentes, es por eso que es muy rápido. Si un enlace se cae, se activa el respaldo en milisegundos.
	- Evita bucles pero muy rápido, casi instantáneamente.
- **MSTP - Multiple Spanning Tree (802.11s):** Como ambos protocolos STP y RSTP crean el mismo árbol para toda la red, es decir, los cables bloqueados afectan a toda la red, el mstp permite crear varios árboles independientes. Los árboles independientes permiten que el mismo cable pueda estar activo para una VLAN e inactivo para otra VLAN.
	- Evita bucles optimizando el tráfico por cada VLAN.

![[Pasted image 20260525114114.png]]

Ahorro de energía en 802.11
1. **PSM - Power Save Mode:** Consiste en que cuando una estación entra en modo de ahorro de energía, envía un mensaje al AP avisándole de su estado. Entonces el AP sabe que la estación existe pero estará inactiva por un tiempo. Por lo que si el AP recibe un mensaje para esa estación, manda un aviso junto con el mensaje. La estación se despierta cada cierto tiempo, si recibe el mensaje junto con una trama entonces se despierta y envía al AP el aviso de que se despertó y está listo para recibir el mensaje.
2. **APSD - Automatic Power Save Delivery:** El envío automático en ahorro de energía permite el envío inmediato de las tramas al cliente después de que se haya enviado el mensaje durante periodos de tiempo programados o no programados.

![[Pasted image 20260525114456.png]]

ALOHA puro vs ranurado
- **Aloha puro:** tiene una eficiencia de $1/2e$ debido a que el tiempo de vulnerabilidad en este tipo de aloha es el doble del tiempo de propagación. Las tramas se envían durante periodos de tiempo largos.
- **Aloha ranurado:** tiene una eficiencia del $1/e$ debido a que el tiempo de vulnerabilidad de este es igual al tiempo de propagación nada más. Las tramas se envían durante el inicio de cada ranura determinada, entonces el periodo de vulnerabilidad se reduce a la mitad.

![[Pasted image 20260525115959.png]]

Tipos de NAT
- **NAT Estática:** Se establecen relaciones de 1 a 1, quiere decir que ya existe una tabla en la que fueron asignadas las relaciones únicas de cada IP pública a cada IP privada.
- **NAT Dinámica:** Se establecen relaciones muchos a muchos. Se determinan grupos de IPs para grupos de IPs, lo que hace que se asigne una IP solo a aquellas que las necesiten y quieran acceder, entonces al usarse todo se libera la IP para que otra pueda usarla después. Ayuda a gestionar el tráfico de VLANs
- **PAT o NAT con sobrecarga:** Es una NAT con sobrecarga que se encarga de gestionar el acceso de hosts distintos a una misna red a través de los números de puerto disponibles.

>[!note] Explique para que sirve el IEEE 802.11D

**802.11D:** Es el estándar otorgado al STP - Spanning Tree Protocol. Sirve para evitar bucles entre VLANs interconectadas, lo que hace es restringir la bloquear los cables que generan bucles, por lo que si algún cable se suelta o deja de funcionar, el protocolo sabe que puede usar otros cables que generan el mismo camino.

>[!note] Explique las diferencias entre la implementación 1000 BASE-T y 1000 BASE-Tx

- **1000 BASE-T:** Utiliza 2 cables de par trenzado categoría 3
- **1000 BASE-TX:** Utiliza 4 cables de par trenzado categoría 5
Ambos son full duplex y de 100 me como máximo.

>[!note] En una red de ALOHA puro, N estaciones transmiten a 1Mbps tramas de 100 Bytes con una media de 2 tramas por segundo. ¿Cuál es el valor máximo de N?

En el ALOHA PURO se tiene una eficiencia de $1/2e$ aproximadamente 18,4%

- N estaciones
- Velocidad de transmisión: 1Mbps = $10^6$ BPS
- Promedio de transmisión por estación: $\lambda = 2$ tramas/segundo

Cada una de las N estaciones transmite a 1Mbps y cada una de ellas también tiene una media de 2 tramas por segundo, por lo que:

$$N*\lambda = S_{\text{tramas totales}}$$

$$N*2 = \frac{1}{2e}*\frac{10^6}{800}$$
$$N=114,9\text{ estaciones}$$